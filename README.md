# object-detection-python-openCV-keras-CNN

                                                                # Load images from the dataset
- load images from the dataset and shuffle between them
- resize the images ( index [0] refers to the first dimensions size which is 96 px, index [1] refers to the second dimensions size which is 96 px ….. ( (img_dims = (96, 96, 3)  ))
- append image to array and sort it ( each one to it's label ) … ( 1 ) for woman and ( 0 ) for mens.

                                                                      # Preprocess Data

- pre-processing by converting the following lists to array … data = [ ], labels = [ ]
- split the dataset for training and validation (( change woman, men values to [ 1 ] , [ 0 ] ))
- use ( ImageDataGenerator ) to generate many images into one image by changing their angels and size, dimensions.


                                                                      # build the model 

- build the model with the following parameters ( width, height, depth, classes )
* depth ( refers to the 3 RGB channels ) , classes ( for the two classes we work on " woman ", "men" )
- Adjust the model by applying many steps like: 
( MaxPooling2D ) to reduce the noice and unwanted objects in the dataset.
( Dropout ) to deactivate (25%) of the dataset to solve the fitting problems.

                                                                      # compile the model
                                                                      
- optimize the model with the proper ratio of Learning Rate and the number of epochs, batch size. 
- complie the model with Adam optimizer, then train the model by using (fit_generator)
- finaly, train thd model with (fit_generator) and save the model to disk, then plot the training,validation, loss, accuracy.

                                                                      # Apply on camera
                                                                      
- use ( detect_face ) from cvlib to recognize faces from images and identify it.
- draw rectangle over faces by using (cv2.rectangle), then crop the images with the same dimensions and resize it.
- apply gender detection on face with ( model.predict(face_crop)[0] )
- write the labels and confidence above face rectangle 
- finally, show the output in the webcam frame
