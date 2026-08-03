FROM alpine:3.24.1@sha256:28bd5fe8b56d1bd048e5babf5b10710ebe0bae67db86916198a6eec434943f8b

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
