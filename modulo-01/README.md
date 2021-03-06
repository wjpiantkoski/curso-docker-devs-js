# O que é o Docker?
- Plataforma de containerização de software.
- O Docker não deve visualizar o Docker como uma virtualização.

# Qual é a diferença entre o Docker e uma VM?
- A máquina virtual retira seus recursos do host para que possa funcionar.
- O Docker oferece uma camada para que os containers possam utilizar apenas os recursos necessários de seu host, sem que seja preciso rodar outro SO, apenas bibliotecas que são necessárias para que o container funcione.

# Imagens vs Containers
- Imagem é a aplicação que queremos rodar.
- Container é a instância da imagem rodando como um processo.

É possível que vários containers sejam iniciados a partir de uma única imagem.

# Rodando o primeiro container
```
docker run -p 8080:80 nginx
```

## Resultado
![Primeiro container](/modulo-01/assets/screenshots/01-aula07.png)

# Docker CLI
Sintaxe padrão
```
docker <command> <sub-command> (options)
```

Rodar um container a partir de uma imagem
```
docker run <image>
```

Rodar um container em background
```
docker run -d <image>
```

Listar containers em execução
```
docker container ls
```

Listar todos os containers
```
docker container ls -a
```

Executar um comando para um container específico
```
docker container <command> <container-id>
```
```
docker container <command> <container-name>
```

Executar um container que está parado
```
docker container start <container-id|container-name>
```

Exibir detalhes de configuração de um container
```
docker container inspect <container-id|container-name>
```

Exibir estatisticas dos containers que estão rodando
```
docker container stats
```

## Analisando o comando ```docker container run```
### Requisitos da aula
```
docker pull ubuntu
```

Adicionando opções para que o container permaneça disponível para receber interações
```
docker container run -it ubuntu /bin/bash
```

Voltar a interagir com container que está em background
```
docker container attach <container-id|container-name>
```

## Analisando o comando ```docker container exec```
Roda um comando em um container que já está rodando
```
docker container exec <container-id|container-name> <command>
```

## Analisando o comando ```docker container rename```
Renomear o container
```
docker container rename <container-id|container-name> <new_name>
```

## Analisando o comando ```docker container commit```
Criar uma nova imagem a partir de um container modificado.
```
docker container commit -m "commit message" <container-id>
```

## Conhecendo mais alguns comandos
Remover todos os containers parados
```
docker container prune
```

Remover uma ou mais imagens
```
docker rmi <image-names>
```

# Volumes
Persistência de dados fora do container.

Inicializar um container com volume personalizado
```
docker container run -v <path-no-host>:<path-no-container> <image>
```

# Camadas de uma imagem
```
docker image history <options> <image>
```
![Image history](/modulo-01/assets/screenshots/01-aula17.png)

# Teste de portas, formatos e SSH
Imagem utilizada durante a aula
```
docker pull rastasheep/ubuntu-sshd
```
Inicializar container a partir da imagem acima, usando a opção ```-P``` para que o container busque por uma porta disponível automáticamente
```
docker container rum -d -P rastasheep/ubuntu-sshd
```
![Lista de imagens](/modulo-01/assets/screenshots/01-aula18.png)

# Docker network
Rede própria do docker que trabalhará de forma agnóstica ao SO.
- bridge (default)
- host
- overlay

Listar todas as redes ativas
```
docker network ls
```

Listar detalhes de uma determinada rede
```
docker network inspect <network-name>
```

Adicionar container a uma rede
```
docker network connect <network-name> <container>
```

Remover container de uma rede
```
docker network disconnect <network-name> <container>
```

  