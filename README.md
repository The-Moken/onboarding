# Environment setup instructions

## Requirements
First, install and set up PostgreSQL (https://wiki.archlinux.org/title/PostgreSQL). Make sure you can run commands like createdb and dropdb to make sure it's working.

## Repos
Download the repos from GitHub (once you have access):
1. https://github.com/The-Moken/monke This is the repo for the backend, you will need to make a Python environment and install the requirements from requirements.txt and requirements-dev.txt on it.
2. https://github.com/The-Moken/moken-platform-client This is the repo for the frontend currently in use.
3. https://github.com/The-Moken/react-flatpickr This needs to be set on the parent directory of the frontend project and built before building the frontend project as it is a requirement. Will disappear in the future when we change the calendar component for the library one.

## Running a local instance of the platform

### Running the backend
To run the backend, first create the database in which we will store the test data for your local instance with

`createdb moken_prod`

Now configure the database by running, on the backend folder (and within the python env):

`python manage.py migrate`

Now load the test data with

`python manage.py loaddata mokenapp/fixtures/*.json && python manage.py loaddata mokenapp/fixtures/test_data.yaml`

Now you can run the server locally with

`python manage.py runserver`

### Running the frontend
First, build the [react-flatpickr](https://github.com/The-Moken/react-flatpickr) with

`yarn && yarn build`

Then from the frontend project folder, run `yarn` once to install the dependencies, then

`yarn start`

to start the frontend server.

You can now access the platform by going to localhost:3000/

You will be redirected to a login page. Two test accounts you can use are:

    davidaiza   OHeY6yaAsJa1wCWUXI4Q
    sofiasaiz   pcsATwjkn0bss7bbUevw
