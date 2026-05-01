git init
git status 
git add .
git commit -m "uday"
git remote add origin https://github.com/UdayKumar2007/idhi.git
git branch -M master
git push -u origin master

for add extra data------------------------------

git add .
git commit -m "vinnu"
git push -u origin

for branch------------------------------------

git checkout -b "MITS"
git branch
git checkout master
git merge MITS
git checkout -d MITS

for cloning--------------------------------

git clone https://github.com/UdayKumar2007/idhi.git

for read all records-------------------

git log


-----------------------------------------------

# Create project folder
mkdir docker-webpage && cd docker-webpage

# Create index.html
echo '<!DOCTYPE html>
<html>
<head>
<title>Hello, World!</title>
</head>
<body>
<h1>Hello, World!</h1>
</body>
</html>' > index.html

# Create Dockerfile
echo 'FROM nginx:latest
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80' > Dockerfile

# Build image
docker build -t my-html-app .

# Run container
docker run -d -p 8080:80 my-html-app


-----------------------------------------------------

# Create project folder
mkdir alpine-nano && cd alpine-nano

# Create Dockerfile
echo 'FROM alpine:latest
RUN apk add --no-cache nano
CMD ["/bin/sh"]' > Dockerfile

# Build image
docker build -t alpine-nano .

# Run container
docker run -it --name nano-container alpine-nano

# Inside container run:
nano --version
nano testfile.txt
# (Type something → Ctrl+X → Y → Enter)
cat testfile.txt
exit

# Cleanup (optional)
docker rm nano-container
docker rmi alpine-nano

---------------------------------------------------

# Pull MySQL image
docker pull mysql:latest

# Run container
docker run --name mysql-container -e MYSQL_ROOT_PASSWORD=root -d mysql:latest

# Access MySQL
docker exec -it mysql-container mysql -uroot -proot

# Run inside MySQL:
CREATE DATABASE student_db;
USE student_db;
CREATE TABLE students (
id INT AUTO_INCREMENT PRIMARY KEY,
name VARCHAR(50),
age INT
);
INSERT INTO students (name, age) VALUES ('John Doe', 22);
SELECT * FROM students;
EXIT;

# Stop and remove
docker stop mysql-container
docker rm mysql-container
docker rmi mysql:latest

------------------------------------

# Create network
docker network create mynetwork

# Run MySQL container
docker run --name mysql-container --network mynetwork \
-e MYSQL_ROOT_PASSWORD=root \
-e MYSQL_DATABASE=mydb \
-d mysql:latest

# Run phpMyAdmin container
docker run --name phpmyadmin-container --network mynetwork \
-d -e PMA_HOST=mysql-container \
-p 8080:80 phpmyadmin/phpmyadmin

