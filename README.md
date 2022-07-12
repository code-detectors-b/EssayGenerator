# Code-Detectors Batch B : Essay Generator
### About the Team
#### Lauren:
Project Manager, Back-end developer, Pre-processing team
#### Evelyn: 
Front-end developer
#### Pooja: 
Back-end developer, Front-end developer, Project Manager
#### Arya:
Pre-Processing team
#### Karishma: 
Front-end developer

### How to Use
To properly use our essay generator you have to first select if you want a claim, rebuttal, evidence, conclusion, or counterclaim. Then, you can select how many of those statements you desire. Next, you enter a statement of your choosing and click on the generate button to generate your prompt. After you’ve completed those steps, your essay should be printed below the generate button. 

### Technical Stack
Html
CSS
Bootstrap
Python3
Flask

### Dataset
We used a dataset called Evaluating Student Writing: Analyze argumentative writing elements from students grade 6-12 from Kaggle. This dataset’s test set has approximately 10K documents. It gives an output of a few lines of text that is generated based on the statement type and prompt given. We are giving the user the choice of what type of statement they want to generate and how many of those statements they would like.  

### Type of Model
We used the GPT-2 NEO and AI textgen models. These models generate text quickly and have a  better memory efficiency. With transformers, aitextgen preserves compatibility with the base package and allows you to use it for different tasks. With pytorch-lightning, aitextgen trains models not just on CPUs and GPUs, but also multiple GPUs and (eventually) TPUs. The input dataset is its own object, allowing you to not only easily encode megabytes of data in seconds, cache, and compress it on a local computer before transporting to a remote server, but you are able to merge datasets without biasing the resulting dataset, or cross-train on multiple datasets to create blended output.

### Libraries Used
We used several libraries for our project. To read and clean our data set, we used the Pandas library. Then, to connect the back-end and front-end of the project, we used the Flask library. We also used AI text gen to generate the text and OS library to work with the CUDA. These were the major libraries that we worked around.. 

If you have any questions, feel free to open an issue on [Github](https://github.com/organization-x/omni/issues).

### Video Guide
[![Deploy a Web Project with Flask](https://img.youtube.com/vi/JUb-PpejA7w/0.jpg)](https://youtu.be/JUb-PpejA7w "Deploy a Web Project with Flask")

This guide covers how you can quickly deploy most projects with the [Flask](https://flask.palletsprojects.com/) framework and our omni scaffold.

### Quickstart Guide for Local Development

cd into the `/app` folder

`python3 -m pip install -r requirements.txt`

edit line 29 the `main.py` file to either the URL of the cocalc server you are on or `localhost` if you are running it on your own PC

run
 
 `python3 -m main`

to start the server on local, most changes while developing will be picked up in realtime by the server

### Quickstart Guide for Local Deployment

Make sure docker is installed on your system. Look that up if you don't know what that means.

cd into the root director of the repo then run 

`docker build -t omni .`

once built, run

`docker run -d -p 9000:80 --restart=unless-stopped --name omni omni`

you should then be able to see the `omni` container running when you run 

`docker ps -a`

if it seems to be stuck (i.e. constantly listed as `Restarting`), something is wrong with the docker image or code inside causing it to repeatedly fail.

you can start debugging the project by running 

`docker logs -f omni` 

or

`docker exec -it omni /bin/bash` for an interactive bash terminal (this option only works if the container is running and not stuck in a restart loop)

### Common Issues

`$'\r': command not found` when attempting to start docker container

this is caused by the the `entrypoint.sh` script somehow having CLRF line endings instead of LF line endings.

to fix this run

`sed -i 's/\r$//' entrypoint.sh`

### File Structure
The files/directories which you will need to edit are **bolded**

**DO NOT TOUCH OTHER FILES. THIS MAY RESULT IN YOUR PROJECT BEING UNABLE TO RUN**

- .gitignore
- config.py
- Dockerfile
- READMD.md
- entrypoint.sh
- nginx_host
- host_config
- app/
     - **main.py**
     - **pytorch_model.bin** <- you will need to upload this yourself after cloning the repo when developing the site
     - **requirements.txt**
     - **utils.py**
     - templates/
          - **index.html**
### pytorch_model.bin ###
The weights file - must upload if you are running file on coding center or are trying to deploy.
### main.py ###
Contains the main flask app itself.
### requirements.txt ###
Contains list of packages and modules required to run the flask app. Edit only if you are using additional packages that need to be pip installed in order to run the project.

To generate a requirements.txt file you can run

`pip list --format=freeze > app/requirements.txt`

the requirements.txt file will then be updated. Keep in mind: some packages you install on one operating system may not be available on another. You will have to debug and resolve this yourself if this is the case.
### static/ ###
Contains the static images, CSS, & JS files used by the flask app for the webpage. You will need to create this and put files in it. Place all your images used for your website in static/images/ so that you can then reference them in your html files.
### utils.py ###
Contains common functions used by the flask app. Put things here that are used more than once in the flask app.
### templates/ ###
Contains the HTML pages used for the webpage. Edit these to fit your project. index.html is the demo page.
### Files used for deployment ###
`config.py`
`Dockerfile`
`entrypoint.sh`
`nginx_host`
`host_config`
**Only modify `host_config`. Do not touch the other files.**
