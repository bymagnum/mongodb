# mongodb install Ubuntu

Официальный репозиторий
<pre>
sudo apt install mongodb-server
</pre>

Состояние службы
<pre>
sudo systemctl status mongod
</pre>

Автозагрузка
<pre>
sudo systemctl enable mongod
</pre>

Вход
<pre>
mongo
mongo --authenticationDatabase "admin" -u "Admin" -p
</pre>

Переключиться в базу admin
<pre>
use admin
</pre>

<pre>
db.createUser({
  user: "Admin",
  pwd: passwordPrompt(),
  roles: [{ role: "userAdminAnyDatabase", db: "admin"}, "readWriteAnyDatabase"]
})
</pre>

Выход
<pre>
quit()
</pre>

Открыть конфиг
<pre>
sudo nano /etc/mongod.conf
</pre>

Найти
<pre>
security:
  authorization: enabled
   
net:
  port: 27017
  bindIp: 127.0.0.1,ip_server
</pre>

Перезагрузить
<pre>
sudo systemctl restart mongod
sudo systemctl status mongod
</pre>

Посмотреть 
<pre>
show databases
</pre>
