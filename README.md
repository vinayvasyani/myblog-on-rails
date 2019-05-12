# README
Root Route, Git and Version Control - Text directions and references
To set root route to pages controller home:

Navigate to config/routes.rb file and enter in the following code ->

root 'pages#home'

The reference to the root path within the application code would be root_path

git config --global user.name "Your name"

git config --global user.email "Your email"

replace Your name and Your email above with your actual name and email address which you want shown on repo

To display git config settings:

git config --list

Some useful git commands:

To generate ssh key:
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

To initialize a git repository for your application (do this from within the application directory) ->

git init

Note: if using Rails 5, your application will already come with a git repository initiated, if you initiate a new one, it'll simply do the same step again

To add/track all files ->

git add -A

To commit changes/updates/additions to repository ->

git commit -m "A useful message to help remember details of commit"

--Setup Github Repository - Text directions and references ----- 
To display your public SSH key:

cat ~/.ssh/id_rsa.pub

When creating github repo for application ensure you click the SSH button then push existing repo:

git remote add origin git@github.com:vinayvasyani/myblog-on-rails.git

git push -u origin master # Remember you only need to use this command the first time

To view remotes setup in your environment (from your app directory):

git remote -v

For future pushes to repository:

git push

To deploy app to production, we'll use heroku in this course, link to heroku:

www.heroku.com

-------Deploying on Heroku Commands -- 
group :production do

gem 'pg', '~> 0.11'

gem 'rails_12factor'

end

If using Rails 5, then

group :production do

gem 'pg', '~> 0.11'

end

- Save Gemfile

- Run bundle install --without production to update Gemfile.lock file

- Commit your changes to git repo ->

git add -A

git commit -m "Make app production ready"

Command to install heroku toolbelt to your local environment, cloud9 already has the heroku toolbelt installed, you can check it by typing in heroku --version:

wget -qO- https://toolbelt.heroku.com/install-ubuntu.sh | sh

Check heroku:

heroku -v

heroku version

heroku # for list of common heroku commands

From your app directory:

To login to your heroku account from your env ->

heroku login

To add your SSH key to your heroku account so you don't have to use username and password everytime ->

heroku keys:add

To create a new production version of your app hosted in heroku ->

heroku create

To push your application code to heroku (deploy your app) ->

git push heroku master

Ensure you have committed all your local changes to your git repo prior to pushing to heroku by checking git status

To change the name of your application ->

heroku rename newnameofyourapp

replace newnameofyourapp above with the name you'd like to give your app

Your app will then be accessible from the following browser URL ->

