
## Every time you start developing...
macOS or Linux Distributions
--- 
- Activate your virtual environment for this project: 
> source venv/bin/activate 
- Point Flask to your application: 
> export FLASK_APP=main.py
- Enable hot reloading, debug mode, and other useful features for local development:  
> export FLASK_ENV=development
- run your flask application: 
> flask run 

On Windows
--- 
- Activate your virtual environment for this project: 
> env\Scripts\activate.bat
- Point Flask to your application: 
> set FLASK_APP=main.py
- Enable hot reloading, debug mode, and other useful features for local development:  
> set FLASK_ENV=development
- run your flask application: 
> flask run 


# Before you start... 
You should have:
- Python 3.8.x installed on your computer 
- Visual Studio Code (or another IDE of your choosing) installed on your computer 
- A GitHub account 
- A Google Cloud Platform account (with class credits)

# Install & Setup

#### Make this website your own: 
- Fork this repository into your GitHub account 
- Clone _your_ version onto your computer 

#### Setup for local development: 
- Open your working directory in VS Code
- Open a terminal in vscode, too. 
- Create a new virtual environment using Python 3.8.x: 
    > python3.8 -m venv venv 
- Download the python modules listed in requirements using pip
    > pip install -r requirements 
- Run the local development server and make sure it all works. 
    > export FLASK_APP=main.py
    > flask run 

You should be able to run the website locally and see it in your local browser.

#### Setup Continuous Deployment
- Set everything up on google cloud like we did in class 
- Add your service account's secret key to GitHub
- Your forked repository should be able to deploy to a live server now


## while developing: 
- Test your app: 
> pytest --doctest-modules
- Lint your app: 
> flake8 --exclude venv 



### To set this up, I did:

python3.8 -m venv venv 
source venv/bin/activate
pip install flask
pip freeze >> requirements.txt  

add new python path to vscode 