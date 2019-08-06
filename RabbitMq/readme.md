Скачать docker.
В cmd комманда docker pull rabbitmq:3-management для скачки образа rabbitmq

Если есть .tar файл
$docker load --input {имя файла}.tar

Комманда для запуска rabbitmq
docker run -d --hostname my-rabbit --name some-rabbit -p 8081:15672 -p 5672:5672 rabbitmq:3-management

Лог и пароль при входе на localhost:8081 (порт можно поменять при запуске)
log: guest
password: guest

Если хотим удалить стандартного пользователя docker exec some-rabbit rabbitmqctl delete_user guest

(Необязательно)
Создание виртуального хоста: docker exec some-rabbit rabbitmqctl add_vhost

Создание пользователя
1 Админ
2 имеет разрешения на взаимодействие с RabbitMQ на уровне приложения. Он будет иметь права на чтение / запись на виртуальный хост.

# Admin user
docker exec some-rabbit rabbitmqctl add_user adminuser MyPassword1
docker exec some-rabbit rabbitmqctl set_user_tags adminuser administrator

# Application user
docker exec some-rabbit rabbitmqctl add_user newuser SuperPassword1
docker exec some-rabbit rabbitmqctl set_permissions -p / newuser ".*" ".*" ".*"