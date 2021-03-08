# DBMS_tutorial
資料庫管理系統安裝教學

## Docker
詳見 docker [官網](https://www.docker.com/products/docker-desktop)

請點選自己電腦的作業系統類型後安裝即可

## MySQL
詳見 docker 官網上的 mysql image 解說
https://hub.docker.com/_/mysql

請不要使用 8.0 經測試目前尚有 bug 導致無法正常運作

於終端機(macOS: terminal, windowsOS: cmd, 命令提示字元)中輸入以下指令將 image 下載下來並執行(以 5.7 版本為例)

```
docker container run -d --name mysqldb -p 3306:3306 -e MYSQL_ROOT_PASSWORD=password mysql:5.7
```

以上指令參數解說：

+ -d (讓服務背景執行)

+ --name mysqldb (將 image 名稱設為 mysqldb)

+ -p 3306:3306 (將本機 3306 與 image 中的 3306 端口做對接，3306 為 mysql 預設的服務端口)

+ -e MYSQL_ROOT_PASSWORD=password (將 mysql root 密碼設為 password)

+ mysql:5.7 (使用 mysql5.7 image)


接著使用 docker ps -a 確認是否有出現該服務

```
zhangtengde-MacBook-Pro:~ zhangteng$ docker ps -a
CONTAINER ID   IMAGE                                        COMMAND                  CREATED          STATUS                     PORTS                               NAMES
030f90ab9826   mysql:5.7                                    "docker-entrypoint.s…"   30 minutes ago   Up 30 minutes              0.0.0.0:3306->3306/tcp, 33060/tcp   mysqldb
```

如果顯示如上，表示已經成功安裝 mysql，並且已經成功啟動。


