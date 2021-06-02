Pandas-Docker
=============

A Docker container for apps that use pandas python module in Python3.8
----------------------------------------------------------------------
```
# First create the container
docker build -t pandas-image .

# Then run the container (replace full path to local-storage with proper path)
docker run -v /Users/bsloan/swdevl/tag-docker/local-storage:/docker-storage -it pandas-image
```

Then, once the container is running:
```
mkdir -p /docker-storage/site-packages
pip install pandas -t /docker-storage/site-packages
```

When that's done you may see that the site-packages directory contains pandas and all dependencies:
```
ls -l /docker-storage/site-packages
```

To verify that pandas imports properly you'll need to set your PYTHONPATH and run python:
```
export PYTHONPATH=/docker-storage/site-packages
python3.8

>>> import pandas as pd
>>> exit()
```

When you're ready to exit the container:
```
exit
```

You will find pandas module and all of its (Ubuntu) dependencies here:
```
ls -l local-storage/site-packages
```
