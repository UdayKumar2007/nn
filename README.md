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

