
# GIT LABORATORY

## REQUIREMENTS

For install this laboratory in your machine you need have installed vagrant in you machine, also, is required 2 GB of memory (recomended 4GB) and 20 GB of free space in disk

After clone the repository, only is necesary run the command `vagrant up` in the repo directory, after finished the command the machine is created, you only need access to http://localhost from your computer to see the home page of your gitlab installation, where you can configure the root password of your installation.

Also you can access to your installation execution the command `vagrant ssh`

> This installation is only for lab enviroment, for production enviroment is recomend a custom installation with HA of all components.

## FIRST STEPS

Once our installation is working, and we access first time to our GITLAB al `http://localhost` we have configure our `root` user with the password saved in our first access.

First we are going to configure the personal-token of root user to have enable the gitlab api, for this we have to go to `Settings` > `Access Tokens`, and create and access token with name **provisioning** and scopes: **api, sudo, read_repository**, after that we have to copy the bearer and save it. When we want access to api (for example with postman), is necessary configure a header Private-Token with the bearer generated previously (the root api of gitlab is http://localhost/api/v4).

> All API is well documented at https://docs.gitlab.com/ee/api/

With this installation, under `provisioning` directory, is attached a file `initial_setup.yml` that create a custom environment of groups, users, etc. (for testing purpose)
