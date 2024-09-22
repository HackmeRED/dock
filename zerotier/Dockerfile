FROM ubuntu
RUN sed -i "s#archive.ubuntu.com#mirrors.ivolces.com#g" /etc/apt/sources.list.d/ubuntu.sources &&\
    apt-get update &&\
    apt-get install -y curl &&\
    curl https://install.zerotier.com > /zt.sh &&\
    bash /zt.sh &&\
    rm -rf /var/lib/apt/lists/*
RUN echo '#!/bin/bash' > /init.sh &&\
    echo 'exec zerotier-one' >> /init.sh &&\
    echo 'sleep inf' >> /init.sh &&\
    rm -rf /var/lib/apt/lists/*

CMD ["sh","/init.sh"]
