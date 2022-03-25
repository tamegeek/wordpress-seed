# WordPress Seed
WordPress Docker Seed for Shared Development

# Before Start-up
This development environment has been set up to use DNSMASQ for the URLs meaning that the container will not be visabile at `http://localhost:8000` instead will be at `http://projecttitle.test`. I advise that you change this to match your project name. You'll need to do so in the '.env.local' file in the 'web' folder and in the database after seeding the project. 
To set up DNSMASQ on your system, there's a step by step guide for the Mac here: https://getgrav.org/blog/macos-monterey-apache-mysql-vhost-apc you'll need to scroll down to the DNSMASQ section. 
# Start-up
This seeder allows for the creation of a WordPress development environment quickly that can also be shared with teams, as the database is exported on the closing of the docker container. (The data folder has been removed from the deployment script examples.)

To get started with this seeder, you will need to run `composer install` to get all of the dependancies and the base build plugins. 
After this, run `docker-compose up -d`. There will be a blank starter database already installed to allow you to start development. 

You'll then need to `cd` into the `web` folder and create a symlink for the .env file `ln -s .env.local .env` should do the job. (remember this will be need when runing an intital deployment to development and production environments.) 

Prior to loading the site up, go into the database with a tool like Sequel Pro and change the URL of the site in the seeded database. Either through a find and replace in Sequel Pro or exporting the database and doing it in a text editor and re-importing the database. 