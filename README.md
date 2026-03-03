https://www.markdownguide.org/basic-syntax/

https://git-scm.com/docs

### to create authentication token in GITHUB and then add the authentication token in cli
https://github.com/settings/tokens<br>
1st click on create token<br>
next step: click on (Only select repositories)<br>
next step: click on permissions<br>
next step: select contents<br>
next step: select read and write next in access drop down menu<br>
final step: generate token<br>
### after the above, do this step in cli
git branch<br>
git push -u origin main<br>
add username:<br>
paste the token: <br>


###
git config --global --unset credential.helper <br>
rm -rf ~/.git-credentials


### 
git branch<br>
git push -u origin main

### to check which username and email is being used
git config user.name<br>
git config user.email


### To Lists all configured remote repositories for your current Git repo.
root@terra:~/gittesting/testing# git remote -v <br>
origin  https://github.com/mussawirimam/testing.git (fetch)<br>
origin  https://github.com/mussawirimam/testing.git (push)<br>
root@terra:~/gittesting/testing# <br>
