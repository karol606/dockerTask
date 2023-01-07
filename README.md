# Task
## 1. Build a docker images that would serve simple web app (simple test html).
## 2. Using either Nginx or Apache with HAProxy as Load balancer for at least two backend serves. 
## 3. HAProxy should be responsible for terminating SSL.
## 4. The CI should contain the build process for the images and pushing to Docker Hub.
## 5. Provide docker-compose file for easy deployment.
## 6. Repository should be public so we can see the process of development.
## 7. Doc.
Task | Do |
--- | --- |
1 | DONE |
2 | DONE |
3 | DONE |
4 | DONE |
5 | DONE |
6 | DONE |
7 | DONE |

## DOC
### 1. File or directory
.github -> Folder with CI definition files. <br>
loadBalancer -> Folder with nginx definition along with certificate. <br>
tomcat -> Folder with server definition with simple interface. <br>
docker-compose.yaml -> Task execution file. <br>
Makefile -> Launchers. <br>
README.md -> Documentation and tasks. <br>

### 2. Use to start
Use the command
```
make start
```
in the folder with the makefile.
The version of the running image is replaced in the docker-compose.yaml file in three places marked <VERSION>.
```
loadBalancer:
  image: acnologia606/nginx:<VERSION>
  ports:
   - "443:443"
   - "80:80"
  links:
   - tomcat1:tomcat1
   - tomcat2:tomcat2
tomcat1:
  image: acnologia606/tomcat:<VERSION>
tomcat2:
  image: acnologia606/tomcat:<VERSION>
```
### 2. Use to stop
Use the command
```
make stop
```
in the folder with the makefile.

### 3. Budowanie i dodaweanie do repopzytorium obrazów 
It all starts with adding a commit to the project.
Image repository link:
nginx -> https://hub.docker.com/repository/docker/acnologia606/nginx/general <br>
tomcat ->  https://hub.docker.com/repository/docker/acnologia606/tomcat/general <br>
