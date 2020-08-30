# DIPY NN Registration API

The code that I first implemented was written in TF 2 with custom training and testing loops. So I refashioned the code to follow the API in [dipy.nn.model.py](https://github.com/dipy/dipy/blob/master/dipy/nn/model.py), with some minor additions and changes.

#### Usage 
```python
from dipy.nn.registration import UNet2d
from dipy.nn.metrics import normalized_cross_correlation_loss
from dipy.nn.registration import RegistrationDataLoader


# Create the data loader objects that fetch and preprocess 
# batches of images for real-time data feeding to our model.
# Moving images: moving_train, moving_val, moving_test
# Static image: static
train_loader = RegistrationDataLoader(moving_train, static,
                                      batch_size=8, shuffle=True)
val_loader = RegistrationDataLoader(moving_val, static,
                                    batch_size=8, shuffle=True)
test_loader = RegistrationDataLoader(moving_test, static,
                                    batch_size=8, shuffle=True)
# The loss function
loss = normalized_cross_correlation_loss()
 
# Instantiate and compile the model with the loss and the optimizer.
model = UNet2d(input_shape=(32, 32, 1), loss=loss, optimizer='adam')
 
# Training the model
# The history object records the training and validation losses for every epoch.
hist = model.fit(train_loader, epochs=epochs, validation_data=val_loader)
 
# Evaluate on the test set.
test_loss = model.evaluate(test_loader)
 
# Warping a moving image
output = model.predict({'moving': moving, 'static': static})
moved = output['moved']
deformation = output['deformation']

# Saving the trained model
model.save_weights('weights_unet2d.h5')
 
# Restoring the model
model_new = UNet2d(input_shape=(32, 32, 1))
model_new.load_weights('weights_unet2d.h5')
```
  
Link to the Colab notebook -  https://colab.research.google.com/drive/1YnGZX43_UzrtWnqI8ZkzLjvprc2kDGk9?usp=sharing  

Link to PR -  https://github.com/dipy/dipy/pull/2137  

There's also a tutorial available in the PR -  https://github.com/sarathknv/dipy/blob/feat-nn/doc/examples/nn_deformable_registration_2d.py  
