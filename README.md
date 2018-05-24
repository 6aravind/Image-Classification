# Image Classification - Nina vs Justice


- [Transfer Learning](https://medium.com/@14prakash/transfer-learning-using-keras-d804b2e04ef8)
 

- Application:
	Image classification for Faces looks like a interesting problem to try. A decent amount of data is required for training the model, lets use celebrities as a simple google image search is good enough.
	To make it little harder for the model, we will go with look alike celebrities. The first option would be to go for [Will Ferrell and Chad Smith](http://www.hollywood.com/celebrities/15-celebrities-who-look-like-other-celebrities-60200060/#/ms-20516/2), but I'm not very good at differentiating these two. Ooops..
	I have picked [Nina Dobrev and Victoria Justice](http://www.hollywood.com/celebrities/15-celebrities-who-look-like-other-celebrities-60200060/#/ms-20516/30), two reasons for this particular choice are 
  - I'm able to differentiate between these two
  - They are not super famous, so it will be little hard for at least some people.  


- Face Model:
	The [VGG face model](https://github.com/ZZUTK/Tensorflow-VGG-face) is a good starting point. Since the model is trained on huge amounts of data for about thousand categories, we can use this model as a feature extractor. On the top of the original model, we will add few layers to make the model predict only two classes. More information on the [original model](http://www.robots.ox.ac.uk/~vgg/data/vgg_face/).


- Preprocessing images:
	The downloaded images for each person does not include only that person's face, but the face model requires only the face. So we need to do some kind of pre-processing before we feeding the images to the model. This is achieved with the help of [face recognition](https://pypi.org/project/face_recognition/) package. This package recognises all faces in the image but we will take only the first face it identifies, as we had made sure that the only person in the image is one of the two classes to be trained.   
