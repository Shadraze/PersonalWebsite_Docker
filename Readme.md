This project is intended to help people quickly quickly get a wordpress website up.
It dockerizes a wordpress website with nginx for reverse proxy. A certbot container is also included to obtain ssl certs.
This is a starting point for personal webservers, you can add your APIs on top with the reverse proxy.

Demo At: https://prabeshgiri.com.np

# Project Setup
Run the nginxConfLoad_Dev.sh script first to load an ssl-enabled development config for Nginx. Then: 
docker-compose up

If you want to change the config files, they are located at Volumes/nginx

# Certbot
To test run the certbot container for first time certificate creation:
docker-compose run --rm certbot certonly --webroot --webroot-path /var/www/certbot/ --dry-run -d [your domain name] -d [your domain name]

It is crucial to do a dry run the first time as LetsEncrypt provides a limited number of certificates per month per IP. 
Remove the --dry-run flag to actually get the certificate once the output of the dry run is correct.

# Misc
Although, environment files are included in the .env folder for first time development use. Please do setup more secure database credentials.
And, do delete the .env folder once the containers are running when in production!

Shell scripts are included for repetitive tasks.

# Ending Thoughts
The project isn't entirely sufficient and more parts need to be automated.
I am currently working on my own webserver using this project and will be updating the project gradually.
Hopefully, the final product will have everything automated with the layman in mind.
