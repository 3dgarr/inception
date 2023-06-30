all: 
	@mkdir -p /home/edgghaza/data/wordpress
	@mkdir -p /home/edgghaza/data/mariadb
	@docker compose -f ./srcs/docker-compose.yml up -d

down:
	@docker compose -f ./srcs/docker-compose.yml down


stop:
	docker-compose -f ./srcs/docker-compose.yml stop

re: clean  all

clean: down
	@docker system prune -a
	@sudo rm -rf ~/data/wordpress/*
	@sudo rm -rf ~/data/mariadb/*

# Осторожно! Fclean удаляет все образы Docker которые есть на машине!
fclean: stop
	@docker system prune --all --force --volumes
	@docker network prune --force
	@docker volume prune --force
	@sudo rm -rf ~/data/wordpress/*
	@sudo rm -rf ~/data/mariadb/*

.PHONY	: all down re clean fclean stop
