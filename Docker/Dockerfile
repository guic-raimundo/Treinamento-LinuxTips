FROM golang:1.18 AS buildando
WORKDIR /app
COPY . ./
RUN go mod init hello
RUN go build -o /app/hello

FROM alpine:3.18.12
COPY --from=buildando /app/hello /app/hello
ENV AAP="hello_world"
ARG NOME="Guilherme"
RUN echo "Nome: $NOME"
VOLUME /app/dados
CMD ["/app/hello"]
