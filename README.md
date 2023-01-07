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
.github -> folder z plikiem z definicją CI. <br>
loadBalancer -> folder z definicją nginx wraz z certyfikatem. <br>
tomcat -> folder z definicją servera z prostą stroną. <br>
docker-compose.yaml -> plik z uruchomieniem zadania. <br>
Makefile -> dyrektywy uruchamiające. <br>
README.md -> dokumentacja i zadania. <br>

### 2. Use to start
Użyj komendy
```
make start
```
w folderze z plikiem Makefile.
Wersja obrazu uruchomionego jest podmieniana w pliku docker-compose.yaml w trzech miejscach oznaczonych <VERSION>.
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
Użyj komendy
```
make stop
```
w folderze z plikiem Makefile.

### 3. Budowanie i dodaweanie do repopzytorium obrazów 
Całość zaczyna się przy dodaniu commita do projektu.
Link do repozytorium obrazów:
nginx -> https://hub.docker.com/repository/docker/acnologia606/nginx/general <br>
tomcat ->  https://hub.docker.com/repository/docker/acnologia606/tomcat/general <br>
