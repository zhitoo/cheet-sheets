# import
```docker exec -i mysql_container mysql -uroot -psecret mysql < db.sql```
# export
```docker exec -i mysql_container mysql -uroot -psecret mysql > db.sql```

# exprt with mysqldump
```mysqldump -u root -p  secret  db_name > db.sql```

# import with mysqldump
```mysqldump -u root -p secret  db_name < db.sql```


