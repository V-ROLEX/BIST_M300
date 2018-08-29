# BIST_M300
## Command line instructions

Git global setup
git config --global user.name "V-ROLEX"
git config --global user.email "lorisw99@hotmail.com"

## Create a new repository

git clone git@gitlab.com:V-ROLEX/BIST_M300.git
cd Documents/BIST_M300
touch README.md
git add README.md
git commit -m "add README"
git push -u origin master

## Existing folder

cd existing_folder
git init
git remote add origin git@gitlab.com:robin.augstburger/M300.git
git add .
git commit -m "Initial commit"
git push -u origin master

## Existing Git repository

cd existing_repo
git remote rename origin old-origin
git remote add origin git@gitlab.com:robin.augstburger/M300.git
git push -u origin --all
git push -u origin --tags