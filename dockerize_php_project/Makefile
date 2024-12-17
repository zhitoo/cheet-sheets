container_name := name
exec:
	docker exec -it $(container_name) bash
migrate:
	docker exec -i $(container_name) php artisan migrate
migrate-fresh:
	docker exec -i $(container_name) php artisan migrate:fresh
seed:
	docker exec -i $(container_name) php artisan db:seed
shield:
	docker exec -i $(container_name) php artisan shield:install --fresh
install:
	docker exec -i $(container_name) composer install
fresh: install migrate-fresh seed shield
test:
	docker exec -i $(container_name) php artisan test
q:
	docker exec -i $(container_name) php artisan queue:listen --queue=alert,important,default
qr:
	docker exec -i $(container_name) php artisan queue:retry
schedule:
	docker exec -i $(container_name) php artisan schedule:work
