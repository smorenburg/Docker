FROM ubuntu:18.04

RUN apt-get update && \
    apt-get install -y curl apt-transport-https lsb-release gnupg wget unzip vim git && \
    curl -sL https://packages.microsoft.com/keys/microsoft.asc | \
        gpg --dearmor | \
        tee /etc/apt/trusted.gpg.d/microsoft.asc.gpg > /dev/null && \
    AZ_REPO=$(lsb_release -cs) && \
    echo "deb [arch=amd64] https://packages.microsoft.com/repos/azure-cli/ $AZ_REPO main" | \
        tee /etc/apt/sources.list.d/azure-cli.list && \
    wget https://releases.hashicorp.com/terraform/0.12.28/terraform_0.12.28_linux_amd64.zip && \
    unzip terraform_0.12.28_linux_amd64.zip && \
    rm terraform_0.12.28_linux_amd64.zip && \
    mv terraform /usr/local/bin/ && \
    apt-get update && \
    apt-get install -y azure-cli && \
    apt-get clean

RUN git config --global user.name "Robin Smorenburg" && \
    git config --global user.email "robin@smorenburg.io"

CMD /bin/bash