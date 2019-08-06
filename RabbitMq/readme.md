������� docker.
� cmd �������� docker pull rabbitmq:3-management ��� ������ ������ rabbitmq

���� ���� .tar ����
$docker load --input {��� �����}.tar

�������� ��� ������� rabbitmq
docker run -d --hostname my-rabbit --name some-rabbit -p 8081:15672 -p 5672:5672 rabbitmq:3-management

��� � ������ ��� ����� �� localhost:8081 (���� ����� �������� ��� �������)
log: guest
password: guest

���� ����� ������� ������������ ������������ docker exec some-rabbit rabbitmqctl delete_user guest

(�������������)
�������� ������������ �����: docker exec some-rabbit rabbitmqctl add_vhost

�������� ������������
1 �����
2 ����� ���������� �� �������������� � RabbitMQ �� ������ ����������. �� ����� ����� ����� �� ������ / ������ �� ����������� ����.

# Admin user
docker exec some-rabbit rabbitmqctl add_user adminuser MyPassword1
docker exec some-rabbit rabbitmqctl set_user_tags adminuser administrator

# Application user
docker exec some-rabbit rabbitmqctl add_user newuser SuperPassword1
docker exec some-rabbit rabbitmqctl set_permissions -p / newuser ".*" ".*" ".*"