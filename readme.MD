
# Every time you open your IDE or turn on your computer: 
> source venv/bin/activate
> export FLASK_APP=main.py
> flask run 



# Before you start... 
You should have on your computer:
- Python 3.8.x 
- Visual Studio Code (or another IDE of your choosing) 

## Quick start

Make this your own: 
- Fork this repository into your GitHub account 
- Clone _your_ version onto your computer 

Setup for local development: 
- Open the directory in VS Code
- Open a terminal in vscode, too. 
- Create a new virtual environment using Python 3.8.x: 
    > python3.8 -m venv venv 
- Download the python modules listed in requirements using pip
    > pip install -r requirements 
- Run the local development server and make sure it all works. 
    > export FLASK_APP=main.py
    > flask run 





### To set this up, I did:

python3.8 -m venv venv 
source venv/bin/activate
pip install flask
pip freeze >> requirements.txt  

add new python path to vscode 