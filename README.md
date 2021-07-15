# Image of the day (iotd)

This is a simple Django project that makes use of some AWS resources.

It is inspired by https://github.com/realpython/image-of-the-day/ with two differences:
* use more recent versions of Django, Pillow, etc
* use S3 to store images


# Configuration

## Database settings
Define the following environment variables
```
RDS_DB_NAME
RDS_USERNAME
RDS_PASSWORD
RDS_HOSTNAME
RDS_PORT
```

## S3 settings
Define the following environment variable
```
S3_BUCKET_NAME
```


# How to run it locally

**Prerequisites:** you need python 3.7 and pipenv installed. You also need access to an RDS (or any postgresql) database and S3

```
git clone <repo>
cd <dir>
pipenv install
export RDS_DB_NAME=<...>
export RDS_USERNAME=<...>
export RDS_PASSWORD=<...>
export RDS_HOSTNAME=<...>
export RDS_PORT=<...>
export S3_BUCKET_NAME=<...>
pipenv run manage.py migrate
pipenv run manage.py createsu
pipenv run manage.py runserver
```

Now, open http://127.0.0.1:8000/admin, login with `admin`, `admin` and click on the '+ Add' button next to Featured Images
Fill in Name, Tagline and upload one image. Click on 'Save'.
Then navigate to http://127.0.0.1:8000/ and you should see your image.

# How to run tests

