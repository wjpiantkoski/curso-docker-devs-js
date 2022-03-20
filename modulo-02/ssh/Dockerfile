FROM ubuntu:18.04

# atualize o SO
RUN apt-get update

# configura o SSH
RUN apt-get install -y openssh-server vim curl
RUN mkdir /var/run/sshd

RUN echo 'root:root' |chpasswd

RUN sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config
RUN echo 'PermitRootLogin yes' >> /etc/ssh/sshd_config

# adiciona o usuário app
RUN useradd -ms /bin/bash app
RUN adduser app sudo
RUN echo 'app:app' |chpasswd

USER app

# instala NVM
RUN /bin/bash -l -c "curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash"
RUN /bin/bash -l -c ". ~/.nvm/nvm.sh && nvm install 'lts/*'"

USER root

EXPOSE 22

# Cria e configura o ponto de montagem do volume
RUN mkdir /workspace
RUN chmod 777 /workspace

VOLUME /workspace

CMD    ["/usr/sbin/sshd", "-D"]
