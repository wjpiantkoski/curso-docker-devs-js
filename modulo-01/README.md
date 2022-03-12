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