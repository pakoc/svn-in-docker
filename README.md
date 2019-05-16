
# SVN DOCKER

## File Structure
  * data/ - repositories directory
  * dav_svn.passwd - users passwords file
  * dav_svn.auth - file of repo access control
  * dav_svn.conf - configuration of container apache svn server
  * nginx.conf.sample - sample of configuration nginx server on host server as a proxy server

  * svn.docker - docker image file
  * docker-compose.ymp - docker compose file
   
## Installation

1. Install docker and docker-compose
2. Run docker-compose within project directory 
```docker-compose up -d```
3. Configure your nginx proxy server using *nginx.conf.sample* file

## Create new repo

To create new repository use

```docker-compose exec svn svnadmin create /var/lib/svn/new_repo_name```

## Create new user

To create new user or change existing user's password use

``` docker-compose exec svn htpasswd -m /etc/apache2/dav_svn.passwd username ```