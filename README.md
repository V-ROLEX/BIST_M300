# BIST_M300
## Command line instructions

Git global setup<br>
git config --global user.name "V-ROLEX"<br>
git config --global user.email "lorisw99@hotmail.com"<br>

## Create a new repository

git clone git@gitlab.com:V-ROLEX/BIST_M300.git<br>
cd Documents/BIST_M300<br>
touch README.md<br>
git add README.md<br>
git commit -m "add README"<br>
git push -u origin master<br>

## Existing folder

cd existing_folder<br>
git init<br>
git remote add origin git@gitlab.com:robin.augstburger/M300.git<br>
git add .<br>
git commit -m "Initial commit"<br>
git push -u origin master<br>

## Existing Git repository

cd existing_repo<br>
git remote rename origin old-origin<br>
git remote add origin git@gitlab.com:robin.augstburger/M300.git<br>
git push -u origin --all<br>
git push -u origin --tags<br>