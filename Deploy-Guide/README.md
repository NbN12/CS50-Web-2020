# How to deploy your cs50 web to heroku

## Setup

### [Download and Install Heroku](https://devcenter.heroku.com/articles/heroku-cli#download-and-install)
### [Verify installation](https://devcenter.heroku.com/articles/heroku-cli#verifying-your-installation)
```bash
heroku --version
```
### Login to heroku
   ```bash
   heroku login
   ```
### Add Procfile
* Bash
    ```bash
    echo "web: gunicorn (your app name here).wsgi --log-file -" >  Procfile
    ```
* Powershell
    ```powershell
    Write-Output "web: gunicorn (your app name here).wsgi --log-file -" > Profile
    ```
   
### Add requirements.txt
```bash
pip freeze > requirements.txt
```
### Add runtime.txt
* Bash
  ```bash
  echo "python-(insert version here)" >  Procfile
  ```
* Powershell
  ```powershell
  Write-Output "python-(insert version here)" > Profile
  ```

## Deployment

### Create a Heroku App

```bash
heroku create (your app name here)
```

### Add a PostgresSQL database to your app

```bash
heroku addons:create heroku-postgresql:hobby-dev -a (your app name here)
```
