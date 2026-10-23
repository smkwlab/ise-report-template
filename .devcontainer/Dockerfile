FROM alpine:3.24.3@sha256:be2656061b536c1883c4034790e21d0a09c5aaaf51968b89368a3c0371ea2c9a

ENV PATH=/npm/node_modules/.bin:$PATH
RUN apk --no-cache add \
        openssh \
        git \
        bash \
        npm

WORKDIR /npm
COPY ["package.json", "package-lock.json", "/npm"]
RUN npm ci

WORKDIR /workdir

CMD ["bash"]
