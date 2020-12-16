# goAssignment
A demo application that interacts with Kafka (producer & consumer) + Redis

This application has 2 parts
1. **http-server**
2. **kafka-consumer**

The http-server handles 2 routes

1. http://127.0.0.1:8080/produce - this produces an event on kafka of the shape `{ type: "number", number: 123333 }` the kafka-consumer listens to this event and determines whether the number is odd/even and based on that increments (`incr`) a key in redis
2. http://127.0.0.1:8080/ - gives you statistics like `{"requests":12,"even":5,"odd":7}` number of events/requests processed so far, number of odd numbers, number of even numbers


# To run this project

1. git clone https://github.com/bhargesh-11/goAssignment.git
2. Install docker, docker-compose
3. Run docker-compose up
4. Produces an event on kafka using http://127.0.0.1:8080/produce
5. View statistics using http://127.0.0.1:8080/
