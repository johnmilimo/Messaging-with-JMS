# Messaging-with-JMS

## Run ActiveMQ
```
 $ docker-compose up

```
The Web Interface for ActiveMQ is at http://localhost:8161 <br />
username: admin <br />
password: admin <br />

## Run the application
```
$ bash run.sh
```

## Schedule messages

1. First, schedule messages with a long delay e.g 20 minutes <br />
    Number of messages : 10000 <br />
    Delay: 20 minutes <br />
    ```
    $ curl 'http://localhost:8080/schedule?totalMessages=10000&delay=1200000'
    ```
2. Secondly, schedule messages with a short delay e.g 2 seconds. <br />
    Number of messages : 10 <br />
    Delay: 2 seconds <br />

    ```
    $ curl 'http://localhost:8080/schedule?totalMessages=10&delay=2000'
    ```

The point is to demonstrate that activeMQ schedule queue is time-based in the sense that items are ordered based on their delay, hence messages with the shortest delay take precedence.
