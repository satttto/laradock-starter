# laradock

## Docker containers
- nginx
- mysql
- phpmyadmin
- workspace
- docker in docker
- php-fpm

## How to use 
1. Make a project.
```terminal
# you want to change "sample" to something you want
mkdir sample

# go to the directory
cd sample
```

2. Clone it to local
```terminal
# clone
git clone https://github.com/Satttto/laradock-starter

# make an enviroment file based on sample
cp .env.example .env
```

3. Change app name
You can change the name of laravel source　(change app to whatever you want)
```.env
APP_CODE_PATH_HOST=../app
```

4. [option] Change mysql setting
You can change the following configuration （around line 371）
```.env
MYSQL_VERSION=5.7
MYSQL_DATABASE=mysql
MYSQL_USER=user
MYSQL_PASSWORD=password
MYSQL_PORT=3306
MYSQL_ROOT_PASSWORD=rootpassword
```

5. Activate docker
```terminal
docker-compose up -d nginx mysql phpmyadmin
```

6. Go inside the container
```terminal
docker-compose exec workspace bash
```

7. Create a laravel project inside the directory that you defined in step 3.
```terminal
composer create-project --prefer-dist laravel/laravel ./
```

8. App
Go to http://localhost

9. Migration
``` 
php artisan migrate
```
You  can check database on phpmyadmin. Go to http://0.0.0.0:8081/
