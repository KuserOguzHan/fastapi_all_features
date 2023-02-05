main.py: Get, post, update, delete kimilerinin tanimlandigi yerdir.
models.py: Tablonun satir sutun tanimlari bulunur
database.py: Database bilgileri vardir.
response model: Yanlizca belirli bilgileri gormek istedigimiz yer.
router: Daha moduler hala getirmek icin kullaniyoruz.
auth: Giris cikis izni icin gerekli yapilandirmalar var.

# Database oluşturma
'''
docker run --rm -d --name postgresql -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=Ankara06 -e PGDATA=/var/lib/postgresql/data/pgdata -p 5433:5432 -v postgresql13_v:/var/lib/postgresql/data postgres:13
'''
# Create database, user and give privileges
- Open psql  
```
docker exec -it postgresql psql -U postgres 

```
- Create and grant
```
create database traindb;
create user train with encrypted password 'Ankara06';
grant all privileges on database traindb to train;
```
# See the table is created.
```
docker exec -it postgresql psql -U train -d traindb

```

```
select * from create_data;

```

```
docker run --rm --name ml-prediction -p 8002:8000 -d ml-prediction-with-fastapi:1.0

```