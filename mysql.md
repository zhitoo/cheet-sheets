# import
```docker exec -i mysql_container mysql -uroot -psecret mysql < db.sql```
# export
```docker exec mysql_container /usr/bin/mysqldump -u root --password="password" db > db.sql```

# exprt with mysqldump
```mysqldump -u root -p  secret  db_name > db.sql```

# import with mysql
```mysql -u root -p secret  db_name < db.sql```


