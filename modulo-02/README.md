# Dockerfile
Para criar nossas próprias imagens por meio de instruções, como se fosse uma receita, para que o Docker gere uma imagem a partir dos comandos listados.

## Sintaxe
```
# Comments
INSTRUCTION arguments
```

## Instruções 
```FROM``` indica qual será a imagem de origem da nova imagem que está sendo criada.


```LABEL``` adiciona metadados à imagem e devem ser escritos no formato ```"chave="valor"```

### Gerando a imagem
Para gerar a imagem, deve-se utilizar o comando ```docker build```
```
docker build <options> <dockerfile-path>
```

### COPY
Copia arquivos do host para dentro da imagem.

### ADD
Copia arquivos do host ou a partir de uma URL para dentro da imagem.