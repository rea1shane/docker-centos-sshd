.PHONY: build run test

build:
	docker build -t rea1shane/centos-sshd:7 .

run:
	docker run -d \
		--name $(HOSTNAME) \
		--hostname $(HOSTNAME) \
		rea1shane/centos-sshd:7

test:
	@make run HOSTNAME=centos-sshd-7
