## Проект контейнеры и CI/CD для Kittygram.

### Описание проекта: 
```
Настройка запуска проекта Kittygram в контейнерах.
```
```
Настройка автоматического тестирования и деплоя проекта на удалённый сервер.
```

### Стек технологий:

* ##### Python
* ##### Django REST
* ##### Docker
* ##### Nginx
* ##### PostgreSQL
* ##### GitHub Actions
* ##### JS
* ##### Node.js

### Как запустить проект: 

##### Клонировать репозиторий: 
``` 
git clone https://github.com/Excellent-84/kittygram_final.git
```
##### Настроить Docker:
``` 
sudo apt update
sudo apt install curl
curl -fSL https://get.docker.com -o get-docker.sh
sudo sh ./get-docker.sh
sudo apt-get install docker-compose-plugin
```
##### Создать файл .env и указать переменные по примеру .env.example:
``` 
cd kittygram_final
sudo nano .env
```
##### Загрузить образы из DockerHub:
```
sudo docker compose -f docker-compose.production.yml pull
```
##### Остановить и удалить все контейнеры:
```
sudo docker compose -f docker-compose.production.yml down
```
##### Запустить контейнеры из образов в фоновом режиме: 
```
sudo docker compose -f docker-compose.production.yml up -d
```
##### Выполнить миграции: 
``` 
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate 
```
##### Собрать статику:
``` 
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
```
##### Создать суперпользователя (указать логин, e-mail, пароль):
``` 
sudo docker compose -f docker-compose.production.yml exec backend python manage.py createsuperuser 
```

#### Автор [Excellent-84](https://github.com/Excellent-84)