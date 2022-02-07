Following the instructions in the fastai course for deploying a bear classifier using voila and Binder, I deployed a classifier that identifies whether an uploaded image
contains a fossil or not. 

I use Gradient within Paperspace to access the fastai notebooks and adapt them for my own use, and wasn't sure how to use the method described to deploy a notebook as a web 
application using Voila from within the Gradient environment. 

After trawling through the fastai forums, I realised that I did not need to execute the commands to install Voila and connect to a server, as described in the book. 

All I needed to do was to follow the instructions to upload a minimal version of a notebook to Github, and then follow the instructions to set up on Binder. Crucially
you need to provide a requirements.txt file on your Github repo that specifies Voila and the fastai version, Binder will set up an appropriate environment using that
information. Binder also provides you with some markdown text that you can add into your readme.md file, that renders as a binder badge that can be used to launch
your application from the repo. 

The repo for my fossil identifier is at https://github.com/RoyMurphy99/fossilPredict
