Script to automate git commits

create git-push.sh

'''
git add .

echo 'Enter the commit message:'
read commitMessage

git commit -m "$commitMessage"

echo 'Enter the name of the branch:'
read branch

git push origin $branch

''''

OR

'''
echo "Enter your message"
read message
git add .
git commit -m"${message}"
if [ -n "$(git status - porcelain)" ];
then
 echo "IT IS CLEAN"
else
 git status
 echo "Pushing data to remote server!!!"
 git push -u origin master
fi
'''


Make file executable:
chmod +x git-push.sh
or
chmod 755 git-push.sh


sudo cp git-push.sh /usr/bin/git-push.sh
sudo cp git-push.sh /usr/local/bin
