
# Rabbitmq and ETC needs to be started first to make sure that todd server starts properly
start:
	docker-compose up -d rabbitmq etcd
	docker-compose up -d

stop:
	docker-compose down

init:
	@echo "Create Groups agent-dc and agent-hq in Todd"
	@docker exec -it dockercompose_toddserver_1 todd create /root/group-dc.yaml
	@docker exec -it dockercompose_toddserver_1 todd create /root/group-hq.yaml
	@echo "Create Tests in Todd"
	@docker exec -it dockercompose_toddserver_1 todd create /root/test-ping-dns.yaml
	@docker exec -it dockercompose_toddserver_1 todd create /root/test-ping.yaml
	@docker exec -it dockercompose_toddserver_1 todd create /root/test-http.yaml

show-agents:
	docker exec -it dockercompose_toddserver_1 todd agents

show-groups:
	docker exec -it dockercompose_toddserver_1 todd groups

cli:
	docker exec -it dockercompose_toddserver_1 bash
