NETWORK_NAME := wordpressNetwork

SERVICE1_DIR := ../wordpress
SERVICE2_DIR := ../mysql
SERVICE3_DIR := ../phpmydamin
SERVICE4_DIR := ../portainer

COMPOSE_FILE := docker-compose.yaml
COMPOSE_FILE_OVERRIDE := docker-compose.override.yaml

.PHONY: start-project

start-project:
	@docker network create $(NETWORK_NAME)
	@cd $(SERVICE1_DIR) && docker-compose -f $(COMPOSE_FILE) -f $(COMPOSE_FILE_OVERRIDE) up -d
	@cd $(SERVICE2_DIR) && docker-compose -f $(COMPOSE_FILE) -f $(COMPOSE_FILE_OVERRIDE) up -d	
	@cd $(SERVICE3_DIR) && docker-compose -f $(COMPOSE_FILE) -f $(COMPOSE_FILE_OVERRIDE) up -d
	@cd $(SERVICE4_DIR) && docker-compose -f $(COMPOSE_FILE) -f $(COMPOSE_FILE_OVERRIDE) up -d

.PHONY: stop-project

stop-project:
	@cd $(SERVICE2_DIR) && docker-compose -f $(COMPOSE_FILE) -f $(COMPOSE_FILE_OVERRIDE) down
	@cd $(SERVICE3_DIR) && docker-compose -f $(COMPOSE_FILE) -f $(COMPOSE_FILE_OVERRIDE) down
	@cd $(SERVICE4_DIR) && docker-compose -f $(COMPOSE_FILE) -f $(COMPOSE_FILE_OVERRIDE) down
	@cd $(SERVICE1_DIR) && docker-compose -f $(COMPOSE_FILE) -f $(COMPOSE_FILE_OVERRIDE) down
	
	


