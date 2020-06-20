## git server

### init a repository

git init --bare &lt;repository\_name&gt;

this is used to create a new repository on git\_server

git sample


https://agripongit.vincenttunru.com/




## git client

### git clone a repository

git clone 





### git tags

git log --oneline

this is used to see short description commit and their tag

git tag -a &lt;tag_name&gt; -m &lt;message&gt; \[&lt;commit_hash&gt;\]

this is used to add a new tag

git tag \[-l pattern\]

this is used to show tag list

git tag -d &lt;tag\_name&gt;

this is used to delete a log tag

git push --tags

this is used to push tags change to remote. By default the push & pull doesnot update the tags reference

git pull --tags

this is used to pull tags data from remote

