
# Need to start Toddserver twice because it crashs if RabbitMq is not ready
start:
	docker-compose up -d
	docker-compose up -d toddserver

stop:
	docker-compose down

agents:
	docker exec -it dockercompose_toddserver_1 todd agents

cli:
	docker exec -it dockercompose_toddserver_1 bash
