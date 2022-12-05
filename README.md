## Intent

This is a sample project to create and deploy a dockerized 3 tier application.  It is NOT production ready and should not be considered to be production code. It is purely to demonstrate the build / deploy of dockerized applications.  

It is composed of 3 parts:

1. Angular 14 front-end
2. Spring / Maven back-end
3. MySQL 8 database server

## Dependencies

1. Docker Desktop
2. Docker Compose
3. MySQL Workbench
4. Postman

## MySQL

1. `docker compose up -d`
2. `docker exec -it docker-sample-3-tier-db-1 mysql -uroot -p`
3. `update mysql.user set host = '%' where user='admin';`
4. `update mysql.user set host = '%' where user='root';`
5. `docker restart docker-sample-3-tier-db-1`
5. Open up Workbench
6. Create Employee Schema - `CREATE DATABASE "employee-schema" /*!40100 DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci */ /*!80016 DEFAULT ENCRYPTION='N' */;`
6. Create Table Called Employee 
'CREATE TABLE "employee-schema"."employee" (
  "emp_id" INT(11) NOT NULL,
  "first_name" VARCHAR(45) NULL,
  "last_name" VARCHAR(45) NULL,
  "email_id" VARCHAR(45) NULL,
  PRIMARY KEY ("emp_id"));
`
7. Open up Postman, do a GET on `http://localhost:8080/api/employees/` -- The results should be [].  This tests connectivity to the DB.
8. Open up the browser to:  `http://localhost:3000` -- This will show end to end connectivity, no employees, and show an environment variable being used.  
9. Open up Workbench, and add a record or two to the Employee Table