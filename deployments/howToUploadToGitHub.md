# How to upload anything to GitHub

## First install and configure **git**

1. dnf install git
1. git config --global user.name "your username"
1. git config --global user.email "your email address"

## To view your configuration

1. git config --list


## To upload your files

1. head over to your github account
1. create a repository

### Clone the repo

1. navigate to the main page of the repo
1. copy the URL for the repo using SSH or HTTPS
1. open the terminal
1. goto the directory which you want to clone
1. type git clone and paste the URL you copied earlier

#### Example

1. git clone git@github.com:username/reponame.git
1. git add .
1. git commit -m "whatever"
1. git push
1. Now head over to github.com/<your_user_name> and check that the file was pushed
