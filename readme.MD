# Flask Website Starter Template 

This repository is a starter template intended to be forked and used for your own website. The focus here is on having a slim, working, full-stack website which can be (relatively) easily built, tested, and deployed on Google App Engine using GitHub actions. It is meant intended primarily for students of the Foundations of Software Engineering Course run in the spring of 2021 at CODE University of Applied Sciences, based in Berlin, Germany, but run remotely due to the pandemic. This README assume that the reader already has a basic familiarity with a broad range of topics and technologies touched on in that class, so it lacks explanation, but may occasionally make reference to something done in that class. 

## Every Time You Develop on Your Project

Every time you restart your computer or reopen VSCode, you'll have to do a few things. Instructions for macOS and Linux distributions assume you are using a Bash shell. Instructions for Windows assume you are using the Command Prompt. Instructions for other shells can be found online. 

- Activate your virtual environment for this project: 
   
    macOS/Linux: `source venv/bin/activate`
    
    Windows: `venv\Scripts\activate.bat`

- Point Flask to your application: 

    macOS/Linux:  `export FLASK_APP=main.py`
    
    Windows: `set FLASK_APP=main.py`
- Enable hot reloading, debug mode, and other useful features for local development:  

     macOS/Linux: `export FLASK_ENV=development`

    Windows: `set FLASK_ENV=development`
- run your flask application: 

    `flask run`

## While You're Developing... 

Whenever you deploy your code, it will be automatically testing and linted by the GitHub Action. To have a quicker feedback loop and to make sure there are as few surprises as possible, run the same commands locally, too:

To test your app: 

> pytest --doctest-modules

To Lint your app: 
> flake8 --exclude venv 


# Installation Instructions
This will be a quick overview of steps for how to use this template on your own project, but will not be a line-for-line cookbook. You can find deeper explanations, tips, and instructions in the [Foundation's main class repository](https://github.com/DrAdamRoe/foundations-sample-website), used for homework assignments. 

## Before you start... 
You should have:
- Python 3.8.x installed on your computer 
- Visual Studio Code (or another IDE of your choosing) installed on your computer 
- A GitHub account 
- A Google Cloud Platform account (with class credits)

### Make This Your Own

Ready to go? Start by making this project your own:
- Fork this repository into your GitHub account. This is a good time to rename the repository to have the name of your project - but you can do it later, too. 
- Choose (or create) a working directory on your own computer and change directory into it
- Clone _your_ version onto your computer in that working directory.

Now you should be ready to get the starter template running on your computer!

### Get Set Up for Local Development: 
- Open Visual Studio Code, and open the folder containing your locally cloned repository. Before editing the code, make sure everything works as expected, locally at least.  
- Open a terminal in VS Code, too. This should automatically be in the same directory as your repository, if not, you should change directory to be in there. 
- In the terminal, create a new virtual environment for this project, using Python 3.8.x. The exact command will depend on your operating system and setup, but the idea is the same: call the Python executable at the command line (e.g. `python` or `python3.8` or `python3` or maybe `\Python38\python` on Windows). Normally, that will open the Python REPL interface, but we don't want that this time - we want it to create a virtual environment for us. To do that, pass the argument `-m venv`, which tells Python "run the venv module". Then, give it one more argument which is the path to a folder name where the virtual environment will live. For ease and consistency, this should be called `venv` and live in the repository root folder. This command could look like this, in the end, depending on your setup:
    
    > python3.8 -m venv venv 

- Activate your virtual environment (instructions can be found at the top of this readme)
- Download the Python modules listed in requirements.txt using pip. In case you are running Windows, uwsgi isn't availiable, so uncomment it in the requirements.txt. (uWSGI==2.0.19.1 => #uWSGI==2.0.19.1) before you execute the following command: 

    > pip install -r requirements.txt

- Run the local development server and make sure it all works. Instructions can be found at the top of this readme for using Flask's built in development server. Alternatively (only on macOS or Linux), you can use the command `uwsgi` to start your development server: 

> uwsgi --http-socket 127.0.0.1:5000 --wsgi-file great_project/website.py --callable app --processes 4 --threads 2 --stats 127.0.0.1:8181 -H venv/

You should be able to run the website locally and see it in your local browser! 

### Configure Visual Studio Code 

A lot can be said here, but there are a few things that will make your life much easier, and are highly recommended: 

- Enable the [Python Extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python), which will immediately give you coding suggestions and show warnings. 
- Set the linter to `flake8`, the same one we are using at the command line and when we build on Google Cloud (CTRL+SHIFT+P / ⇧⌘P). This will give you visual feedback (yellow and red squiggly lines)
- Set the version of Python (or "interpreter") to be the virtual environment you have just created. (CTRL+SHIFT+P / ⇧⌘P). This will help you to identify mismatches in your setup, especially when importing modules. 

#### Setup Continuous Deployment
You now have a website working locally, congratulations! And you can edit it, too. A website isn't really that useful unless it's on the web, though. A detailed explanation for how to do this can be found on our [Miro Board](https://miro.com/app/board/o9J_lTxsze4=/), in the [Foundation's main class repository](https://github.com/DrAdamRoe/foundations-sample-website), and in Google Classroom (where there is a walkthrough video). As a reminder, the main steps are: 
- Before you start, make sure you are logged into Google Cloud with your university email address, and have redeemed the voucher for free credits. 
- Create a new project on Google Cloud, and enable App Engine and Cloud Build. 
- Create a new service account, and give it the appropriate permissions.
- Create a key for your service account, and add that key as a "Secret" to your GitHub repository.  

GitHub should now be able to deploy your website to Google Cloud, and run it! To test this, you may have to trigger a build. If there is already a failed build (a red x visible on your repository's page), you can click on it and "Re-run jobs". The code itself hasn't changed, but your setup has - so we expect it to work now. Otherwise, you can push your code from your computer to GitHub, and it will trigger a build and deploy. 

At this stage, your website should be running on the internet, live! 

## Make This Repository Your Own

Now that you have verified that this setup works, it is time to make it your own. Here are a few things I suggest changing right away:   
- The repository name, if you haven't yet. 
- Change the title of the index page
- Edit the CSS a little, changing a font or color.
- Rename the folder `great_project` to be your project name. When you do this, you will have to change a few references to the directory: in `app.yaml`, `main.py`, and `test_great_project.py`. You can use the feature `Edit --> Find in Files` to find all occurrences of the name to make sure you have found them all. 

Even before you add any "features", this makes the website and code look and feel more like it is yours already! 

Once you have made some of these small changes, remember to add, commit, and push your changes - and with that, it should automatically be live on the internet! 

### A Few Notes...
Some pieces of this repository may require explaining. Here goes. 

#### Environment Variables 
This setup is designed to allow you t use environment variables if you need them. There are many ways to set this up with Python, and for this repository, I chose a method which allows for relatively simple integration with our GitHub Actions and Google App Engine workflow, but it does not scale very well. A more scalable system using the library `python-dotenv`. If you start working with many secrets, for example, many API keys, it makes sense to switch to that instead. The current system as implemented in this repository is described below.  

Environment Variables can be found in the file `config.py`, as can more explanation. In order to use an environment variable - a value which you expect to be different in local development from our production system - it should be added to that file. In the cases of the Python variable `DATABASE_PASSWORD`, Python will look for an environment variable (on the computer running your website) called `DB_PASSWORD`, and assign its value to the Python variable. This is then usable by the Flask app. It is essential that anything which should remain a secret, like a database password, is never added to your GitHub repository. This makes your password public - giving anyone access to your database. Instead, we can use GitHub Secrets to securely add a password to the production environment. In other words: we can create a database password, add it to GitHub Secrets, and then GitHub can pass it on to App Engine. The last step requires one more trick, though. The App Engine environment is configured by the file `app.yaml`, which does not support reading in environment variables dynamically. Instead, the GitHub Action has a step in it called `Prepare Deployment`, which can add a GitHub Secret to the `app.yaml` file. In this case, the code expects GitHub to have a variable called `PRODUCTION_DATABASE_PASSWORD`. A line of code in `.github/workflows/main.yaml` then adds this password to the file `app.yaml` dynamically, setting to have the name `DB_PASSWORD`. This, in turn, is read in by the flask app. Note that the environment variables can all have the same name, but I have made them different to make it clearer what is what. 

### Databases: What Are My Options? 

If your website needs a database - and most do - you have a few choices. In class, we used SQLite to demonstrate how to integrate SQL with Python, and how to build a simple data model. In practice, we rarely want to use this approach - for reasons of scale, security, and code readability. To make a long story short, the classic approach is to use a relational database like PostgreSQL as your database. It takes on the role that SQLite had in class, but PostgreSQL (or just "Postgres" for ease), is usable in production in a web environment. This is a great approach if you expect users to login, for instance: Postgres can securely and efficiently store user names and passwords, and Flask integrates well with Postgres. There are many explanations out there for how to do this, for instance [here](https://realpython.com/flask-by-example-part-2-postgres-sqlalchemy-and-alembic) or [here](https://towardsdatascience.com/building-and-deploying-a-login-system-backend-using-flask-sqlalchemy-and-heroku-8b2aa6cc9ec3) - though both use other platforms for deployment, the code is very similar to what you could use. The exact setup will be a matter of features and preference, but the core idea is the same. You can use Python libraries to interact with the database, for instance, `psycopg2` and `flask-sqlalchemy`. You can have a local development database server and a production server: these two should have the same structure, but different data. They will also have different locations and passwords, which can be configured through environment variables. For hosting, I would recommend using Google Cloud's managed Postgres service, Cloud SQL, for this - [documented here](https://cloud.google.com/sql/docs/postgres/connect-app-engine-standard). There are other options for hosting, too, but this is the simplest. Note that this setup is common and a good practice, but not all websites need this - and you are not required to have a real database for your project. You are, however, expected to get a basic version of your website running, and the reality is that the vast majority of websites need a database of some kind. 

There are other options for data storage which could make sense, depending on your setup. Here are a few other ideas: 
- If your data is not personal and does not be particularly secure, and you don't expect much of it, you could consider using a Google Sheet as a database. This is not widely practiced but it has some interesting use cases - and it is very easy to setup. An example of how to do this [can be found here](https://betterprogramming.pub/integrating-google-sheets-api-with-python-flask-987d48b7674e). Just remember that this is not very safe or secure, so this method is not appropriate for a website where users login or give private information; it could be used, though, for an anonymous survey, for instance. 
- If your data is not very structured, you can consider using a Document-Based NoSQL database. Generally, these types of databases store information that looks like JSON or a Dictionary; they have advantages and use-cases, too. There are many options here, including Google's proprietary [Datastore](https://cloud.google.com/datastore/docs/quickstart), which can be [integrated into flask](https://cloud.google.com/community/tutorials/using-flask-login-with-cloud-datastore) with relative ease or the open source [MongoDB](https://www.mongodb.com/), which has its own managed database service called [Mongo Atlas](https://www.mongodb.com/cloud/atlas). This can also be integrated easily with Flask using the [flask-mongodb](https://pythonbasics.org/flask-mongodb/) library, in a setup that, in the end, is pretty similar to the one described above using Postgres.



