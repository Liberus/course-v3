# course-v3
The 3rd edition of course.fast.ai - coming in 2019

## This fork contains dockerfile and instruction for it's usage.

What this file does:

* Installs software, which is used and/or mentioned in notebooks
* Install jupyterlab and some handy extensions for better experience. Jupyter notebook should also work but I never tried
* Set’s a jupyter password, so you can acces jupyterlab without token. Changes to jupyter_notebook_config.py should be made in order to enable this. Here is the explanation, what to do https://jupyter-notebook.readthedocs.io/en/latest/public_server.html#preparing-a-hashed-password
* Changes default shell to bash
* Creates another user, this way inside of docker will look more like regular setup
* Sets up conda
* Uses conda to install pytorch, fastai and other usefull packages
* runs jupyterlab by default

Build command: `sudo docker image build -t fastai_v1:v3 .`

I’m running this file executing `sudo docker run -p 8888:8888/tcp -v /home/user/AI:/home/user/AI --runtime=nvidia --ipc=host fastai_v1:v3`

TODO:
- [ ] Add step-by-step instructions how to build and run this dockerfile
- [ ] Add `if` conditions to dockerfile, so it won't fail if no kaggle.json or jupyter_notebook_config.py is provided
- [ ] Test if jupyter notebook works with this dockerfile
- [ ] Add mounting of fast.ai related data directories to external system, so the downloaded files and configs are saved between docker runs
