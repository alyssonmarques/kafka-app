# Kafka-app

## Subir os serviços do Kafka
```
cd docker
docker compose up -d
```
## Para criar um tópico
```
cd app

docker exec broker kafka-topics --create \
    --topic [nome_do_tópico] \
    --bootstrap-server localhost:9092 \
    --replication-factor 1 \
    --partitions 1
```
Obs: não esqueça de alterar o nome do tópico em consumer.go e producer.go

## Para gerar o producer/consumer
```
cd app

go build -o out/producer util.go producer.go
go build -o out/consumer util.go consumer.go
```
## Para produzir/consumir
```
cd app

./out/producer app.properties
./out/consumer app.properties
```
