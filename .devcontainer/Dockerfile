FROM alpine:3.24.4@sha256:93b41ef40b1677fce8fcc64ff4af09daddfacf5040afde618bc46c1e2d1cc7d4

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
