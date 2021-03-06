# ToDo App With Test Cases
## About
This app contains apis for following: 
- [x] Create
- [x] Update
- [x] Retrive
- [x] Delete
- [x] SoftDelete
- [x] Register User
- [x] Forgot_password
- [x] Show Currently login user profile

## Note:
Every Api required JWT Authentication and IsAuthenticated except following:
- Login
- Register
- Forgot Password

# Database
This project used postgres database. 

## Database setup
To install and connecting database with django follow the following steps:
### Install Postgres
**Create the file repository configuration**:


```
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
```

**Import the repository signing key:**


```
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
```

**Update the package lists:**

```
sudo apt-get update
```

**Install the latest version of PostgreSQL.**

```
sudo apt-get -y install postgresql
```

**If you want a specific version, use**:

 ```
 sudo apt-get -y install postgresql-12
 ```
 
 **Install client**
 
 ``` 
 sudo apt-get install postgresql-client
 ```
 
 **Additional supplied modules (part of the postgresql-xx package in version 10 and later)**
 
 ``` 
 sudo apt-get install postgresql-contrib-9.x	
 ``` 
 
 **Libraries and headers for C language frontend development**

``` 
sudo apt-get install libpq-dev 
```

**Libraries and headers for C language backend development**

``` 
sudo apt-get install postgresql-server-dev
```

## Install pgadmin4 
``` 
curl https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo apt-key add - 
```

``` 
sudo sh -c 'echo "deb https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/focal pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list'
```

``` 
sudo apt update
```

```
sudo apt install pgadmin4
```

# Instructions

**Clone Project Using:**

``` 
git clone https://github.com/JunaidAfzalAtArhamsoft/ToDo-Rest-Tests.git
```

**Install Required Libraries**

```
pip3 install -r requirements.txt
```

**Create Migrations**

```
python3 manage.py makemigrations
```

**Migrate**

```
python3 manage.py migrate
```

**Run server**

 ```
 python3 manage.py runserver
 ```
 
 
 # Testing Apis
 
 Use below command to test apis.
 
  ```
  python3 manage.py test
  ```
  If you see error:
  
  ``` Django user has no permission createdatabase ```
  
  Fix it by:
  
  Open terminal by
  ```
  Ctrl + alt + T
  ```
  Run command here
  ```
  sudo -u postgres psql
  ```
 Now run this command here on postgres console
 ```
 Alter User user(database user that set in django settings.py) createDB;
 ```
 Now run the test command again:
 ```
 python3 manage.py test
 ```
 
 ![new test result](https://user-images.githubusercontent.com/93306663/143591169-01f01ba0-0303-4192-b2eb-ed18a2519f6a.png)

 
**Result:  All test passed**
 
# Pylint Testing
 
 
 ``` 
 pylint to_do_api
 ```

 
![new pylint result](https://user-images.githubusercontent.com/93306663/143591234-63bd7971-4f8d-491c-92ca-20988941ff5f.png)


 
 
**Result: 9.97 / 10**
