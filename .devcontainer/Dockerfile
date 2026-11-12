FROM alpine:3.24.4@sha256:f59abe656b692d901e184be3445e084786602108599d2a51d229c0f5a48c71bf

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
