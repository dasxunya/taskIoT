**Для того, чтобы запустить и посмотреть вывод проекта нужно прописать следующие команды:**

1. docker swarm init

2. docker network create --driver overlay --attachable dasxunya-overlay

3. docker compose up

4. docker compose exec -it curl sh

    cd ~

    ./source.sh

    ./target.sh

5. Открываем новый терминал и прописываем:
docker compose exec -it mongodb-source mongosh

Добавление объекта

db.users.insertOne({
  "_id": Number(1),
  "firstname": String("dasxunya"),
  "lastname": String("shap"),
  "age": Number(20),
  "email": String("test@mail.ru")
})

6. Открываем еще один терминал, входим в target-db и смотрим наличие добавленных значений:

docker compose exec -it mongodb-target mongosh

db.users.find()