FROM nvidia/cuda:10.2-devel-ubuntu18.04

ARG ROOT_PATH=/root
ARG DEBIAN_FRONTEND=noninteractive

ENV SHELL=/usr/bin/zsh
ENV TZ=Asia/Seoul

WORKDIR ${ROOT_PATH}

RUN set -eux; \
    apt-get update \
        && apt-get install -y --no-install-recommends apt-utils software-properties-common apt-transport-https ca-certificates \
            zsh time curl wget less openssh-client git tig tmux zip unzip p7zip-full vim htop iftop rsync lynx jq tzdata neofetch \
            iproute2 iputils-ping iputils-tracepath dnsutils net-tools ngrep netcat telnet \
        && apt-get clean && rm -rf /var/lib/apt/lists/* ; \
    wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O /tmp/install-oh-my-zsh.sh \
        && zsh /tmp/install-oh-my-zsh.sh && rm -vf /tmp/install-oh-my-zsh.sh && sed -i '1iDISABLE_AUTO_UPDATE="true"' ~/.oh-my-zsh/oh-my-zsh.sh

CMD ["/bin/zsh"]

