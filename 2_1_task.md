# Выполняем команду:
``` 
docker search postgres
``` 
## Эта команда выполяняет поиск образа в Docker Hub

### Результат: 

<img width="819" alt="image" src="https://github.com/user-attachments/assets/e3d0face-4b57-4940-88f3-5760c15dad98" />

# Далее загружаем образ postgres
```
docker pull postgres
```
### Результат:

<img width="598" alt="image" src="https://github.com/user-attachments/assets/a62e5845-1665-49f2-b2d5-7c10a5173324" />

### Эта команда запустит нам контейнер PostgreSQL в фоновом (detached) режиме и присвоит ему имя test-pg, последней командой проверили, что контейнер запущен:
```
docker run --name test-pg -e POSTGRES_PASSWORD=12345pg -d postgres
```
```
docker ps
```
<img width="744" alt="image" src="https://github.com/user-attachments/assets/72ee924c-ff6e-47de-ac04-acd84f0acb88" />

## Подключились к postgres внутри docker: 
```
docker exec -it test-pg  psql -U postgres
```
## Результат:

<img width="519" alt="image" src="https://github.com/user-attachments/assets/fda83e57-9bb1-45f4-aefa-68acade35414" />
