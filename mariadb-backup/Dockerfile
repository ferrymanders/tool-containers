ARG FROM_TAG=12-noble

FROM mariadb:${FROM_TAG}

RUN echo "# Install dependancies" \
    && apt update \
    && apt install -y \
        curl \
        unzip \
    \
    && echo "# Install AWS CLI" \
    && curl "https://awscli.amazonaws.com/awscli-exe-linux-$(uname -p).zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && ./aws/install \
    \
    && echo "# Cleanup" \
    && rm -rf /var/cache/apt/archives \
    && rm -rf /var/lib/apt/lists/*

CMD ["/bin/bash"]
