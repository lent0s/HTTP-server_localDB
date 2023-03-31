# ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ HTTP-server_localDB
​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​
*simple HTTP-server (CURD) with local DB*  
​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​
![picFile](https://cdn-icons-png.flaticon.com/128/3767/3767084.png)

---

​                      .\cmd\config.ini           ​ ​ ​ ​ ​ ​ // путь для БД и количество попыток инициализации/создания  
​ ​ ​ ​ ​ ​ ​ ​ ​ ​         \main.go          ​ ​ ​ ​ ​ ​ ​ ​ // запуск нескольких `prog.go` в автоматическом режиме  
​ ​ ​ ​ ​ ​ ​ ​ ​ ​         \prog.go          ​ ​ ​ ​ ​ ​ ​ ​ // запуск сервера на указанном порту по флагу -h  
​ ​ ​ ​ ​ ​ ​ ​ ​ ​         \proxy.go           ​ ​ ​ ​ ​ ​ ​ // запуск прокси для `prog.go`

---

​                      .\test\test.go   ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ // случайные рабочие запросы на прокси  
                            ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​
                            ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ // *(для работы **необходим curl**)*

---

http://host/get                              ​ ​ ​ ​ ​ ​ ​ ​ // выводит все записи  
                                   ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​
​ ​ ​ ​ ​  /getAR                                    ​ ​ ​ ​ // выводит все записи с периодом обновления **50мс**  
                                   ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​
​ ​ ​ ​ ​  /exit                             ​ ​ ​ ​ ​ ​ ​ ​ // завершает работу сервера

---

**примеры curl команд:**  

​ ​ ​ ​ ​ ​ ​ ​ ​ **создание записи:**
- curl -X POST    ​ ​ ​ http://localhost:8080/create            ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ -d "{"name": "ANN-MARY",                    "age": 77}"
- curl -X POST    ​ ​ ​ http://localhost:8080/create            ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ -d "{"name": "Bella", ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ "age": 33}"
- curl -X POST    ​ ​ ​ http://localhost:8080/create            ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ -d "{"name": "Chase",     ​ ​ ​ ​ ​ ​ ​ ​ ​ "age": 22}"
- curl -X POST    ​ ​ ​ http://localhost:8080/create            ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ -d "{"name": "Ma BiNT ho",                  "age": 27}"  
​ ​ **изменение:**
- curl -X POST    ​ ​ ​ http://localhost:8080/make_friends                            -d "{\"source_id\": 1, \"target_id\": 2}"
- curl -X PUT ​ ​ ​ ​ ​ http://localhost:8080/1 ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ -d "{\"new age\": 44}"  
​ ​ **уничтожение:**
- curl -X DELETE        http://localhost:8080/user        ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ ​ -d "{\"target_id\": 2}"
