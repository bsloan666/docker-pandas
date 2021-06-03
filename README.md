docker-pandas
=============

A Docker container for apps that use pandas python module in Python3.8
----------------------------------------------------------------------
```
# First create the container
docker build -t pandas-image .

# Then run the container (replace full path to local-storage with proper path)
docker run -v ~/docker-pandas/local-storage:/docker-storage -it pandas-image
```

You will find a zip file with all of your requirements.txt packages and all of their (Ubuntu) dependencies here in your local area:
```
ls -l local-storage/python.zip
```
