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