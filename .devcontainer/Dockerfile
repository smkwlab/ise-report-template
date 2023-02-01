FROM alpine:latest

ENV PATH=/npm/node_modules/.bin:$PATH
RUN apk --no-cache add \
        openssh \
        git \
        bash \
        npm

WORKDIR /npm
COPY ["package.json", "package-lock.json", "/npm"]
RUN npm install /npm

WORKDIR /workdir

CMD ["bash"]
