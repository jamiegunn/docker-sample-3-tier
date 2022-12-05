
##Backend
docker build -t dragonspears/docker-sample-spring .
docker run -d --rm -p 8080:8080 --name backend -e spring.datasource.password=Buster4749! -e spring.datasource.username=admin -e spring.datasource.url=jdbc:mysql://host.docker.internal:3306/employee-schema dragonspears/docker-sample-spring
