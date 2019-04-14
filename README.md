Click [here](https://grammable-zoe-kramer.herokuapp.com/) to visit Grammable.

# Grammable

### Overview

An application, built with Ruby on Rails, that focuses primarily on test driven development. Users are able to upload a picture with a caption which then can be edited or deleted. 

### Code Structure

**Models** - 

*Gram Model* - [`app\models\gram.rb`](https://github.com/ZoeBKramer/grammable/blob/master/app/models/gram.rb)

Handles the validations for entering in a new gram. It also ties the gram to the user who created it and allows it to have many comments. We use the Carrierwave gem to handle the actual photo uploading, using AWS as our storage.

*Comment Model* - [`app\models\comment.rb`](https://github.com/ZoeBKramer/grammable/blob/master/app/models/comment.rb)

Ties the comment to the gram it was posted under as well as the user who posted it. 

*User Model* - [`app\model\user.rb`](https://github.com/ZoeBKramer/grammable/blob/master/app/models/user.rb)

Allows the user to have many grams as well as comments. We use the devise gem in this model to handle user authentication.

**Views** - 

**Controllers** -

**Gemfiles** -

[bootstrap gem](https://github.com/twbs/bootstrap-rubygem) - helps format the page

[simple-form gem](https://github.com/plataformatec/simple_form) - creates the form in which data can be entered into

[devise gem](https://github.com/plataformatec/devise) - we used this gem for the authentication of users

[carrierwave gem](https://github.com/carrierwaveuploader/carrierwave) - provides a simple and extremely flexible way to upload files from Ruby applications

[figaro gem](https://github.com/laserlemon/figaro) - this gem secures sensitive information (ie. secret keys) by not pushing it to Github, only production

[fog-aws gem](https://github.com/fog/fog-aws) - supports Amazon Web Services

[carrierwave-aws gem](https://github.com/sorentwo/carrierwave-aws) - officially supported AWS-SDK library for S3 storage rather than relying on fog

# Set Up Vagrant

Click [here](https://github.com/university-bootcamp/coding-environment/blob/master/windows-vagrant.md) to find the instructions for setting up Vagrant.

### Vagrant

Between each of the coding sessions you do, especially if you restart your machine, you will need to run the following command to start your vagrant environment prior to connecting:

`vagrant up`

When this command completes, run the vagrant ssh command to log in to Vagrant.

After this completes, you will be taken to a coding environment inside your virtual machine, and your terminal should contain the green [ENV].

Running the `killall ruby` command in your terminal should quit all running Rails servers.

**To ensure that your server is not running** -— If you visit the URL [http://localhost:3030](http://localhost:3030) in your browser, you should not see a web page load. You should ensure that your server is not running before starting new server windows.

**If you want to preview the application that is running within your coding environment**—Visiting the [http://localhost:3030](http://localhost:3030) from your web browser will allow you to do this.

All the files within this folder inside the Vagrant environment will be automatically synced outside the Vagrant environment to folder inside the `coding-environment/src` folder that is located outside the virtual machine, usually on your Desktop.

# Set Up Grammable

### Checking Out the Repo

Check this repository out into your `coding-environment/src` folder. 

### Create the Initial Database

Connect to your Vagrant instance, change the directory `cd /vagrant/src/grammable`

Run `rake db:create`

### Starting Up Your Server

In a separate terminal, change the directory `cd /vagrant/src/grammable`

Start your server by running `rails server -b 0.0.0.0 -p 3000`

