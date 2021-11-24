#Fastai setup using Gradient on Paperspace

At the time of me reading Deep learning for Coders with Fastai, the recommended option for running the Jupyter notebooks was to set up a fastai container on
Gradient in Paperspace at Paperspace.com . 

Signing up to paperspace and creating a new fastai container were very straightforward, but as soon as I ran the first notebook I got errors, notably failing
to find a module called torch.fx . 

After trawling through the fastai forums and other sites, the following steps resolved the issue for me:

1. Before running the first notebook, start a new terminal in the fastai container, and type the following commands.
2. pip install fastai fastcore --upgrade
3. git pull
4. pip uninstall torch torchvision torchaudio
5. pip install torch torchvision torchaudio

I think steps 1 to 3 update the fastai libraries to the latest versions, but this results in incompatible versions of some of the packages.
Steps 4 and 5 fix the compatibility issue. 

I hope someone finds this useful. 
