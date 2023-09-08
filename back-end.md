# Back-end



## I. Basic Structure.

1. The Back-end is written in `python` and is written on the `Flask` framework. The `python` version used is at 3.8
2. The `./controllers` folder in each app directory contains all the API routes and loginc.
3. The `./app.py` file contains the base layer where the `Flask` application is initialized.
4. he `./server.py` file contain the code for creating the server and listening to the PORT which is taken from the environment variable, by default it is written to listen to port:8080.
5. Since the Application is written in TypeScript and during development, creating a build each time a change is made is time-consuming, so during development we can use the terminal command `python debug.py` to run the server for hot reloading.
6. The `./controllers` folder contains the resource-based API routes and its prefix is defined in `./urls.py` .
7. Any Configurations such as aws initialization, which configurations are written in `./utils.py`&#x20;
8. The Swagger document is kept in `./static/swagger.json` and initialized in `app.py` file, can be accessed by using the URL: [localhost:8080/swagger](http://localhost:8080/swagger).
9. The Environment variables are never committed and should not be committed, and should be kept in `.env` file in the same level as `env.example` file is kept. The `env.example` file shows the developer the basic environment variables that they need to have in-order to run their server in the local machine.
10. Any middlewares such as authentication and authorization which are kept under `./middlewares` folder.





## II. Development Cycle

When a developer pulls the code for the first time, They can refer to the `README.md` file in order to set up their machine locally.

#### Useful Commands:

```markup
pip install -r requirements.txt  #This install all the nessesary packages needed for the Application
flask db upgrade  #Runs the migrations to your database set in your .env file
python debug.py  #Run the server

```

####

## III. Branching Structure

The important branches are:

1. `dev` : This branch is the development branch that get deployed to Dev instance and the branch from where the devs would cut branches for fixes / features.
2. `staging` : This branch is the staging branch which is deployed to Staging instance where the testers/clients tests the App.
3. `master` : This is the production branch where the latest `staging` branch would get merged and deployed to the production environment.

While working in a fast-paced development cycle, it is always recommended to run the trunk-based strategy for the developers, That is if there is any hotfix / feature branch that is cut from `dev`, after the code is all committed and pushed to the respective feature branch, always rebase that branch with develop and clear all conflicts and force push. Once pushed, test out all the affected areas before putting out a PR.

