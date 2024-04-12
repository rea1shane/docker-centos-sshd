.PHONY: build run test

build:
	docker build -t rea1shane/centos-sshd:8 .

run:
	docker run -d \
		--name $(HOSTNAME) \
		--hostname $(HOSTNAME) \
		rea1shane/centos-sshd:8

test:
	@make run HOSTNAME=centos8
