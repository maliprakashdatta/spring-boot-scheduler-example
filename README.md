# spring-boot-scheduler-example

 ### Technical Details
In this project, we are going to use below set of versions for demonstrations.

    Spring Boot - 3.3.4
    jdk-17

### Building

The example can be built with
```shell
mvn clean install
```

### Running the example in your local
```shell
mvn clean spring-boot:run
```
## dependency
```shell
  <dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-web</artifactId>
</dependency>

<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-test</artifactId>
<scope>test</scope>
</dependency>
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter</artifactId>
</dependency>
```
## Configuration
The main configuration is in src/main/resources/application.properties:
```shell
spring.application.name=spring-boot-scheduler-example
###Logging
logging.level.org.springframework=INFO
logging.level.com.example=DEBUG

### Server
server.port=8090

### Custom scheduler properties
fixedDelay.in.millis
You can modify the fixedDelay.in.milliseconds value to change the delay for the fixed delay task.
```
Explanation of @Scheduled(cron = "0 0 10 * * *"):

## Scheduling with Cron Expression
0: second (at 0 second)<br>
0: minute (at 0 minute)<br>
10: hour (at 10 AM)<br>
*: day of the month (every day)<br>
*: month (every month)<br>
*: day of the week (every day of the week)

### You can adjust the cron expression to fit your needs, e.g.:<br>

"0 0/5 * * * *": every 5 minutes<br>
"0 15 14 * * ?": at 2:15 PM every day

## Key Annotations and Parameters:
@EnableScheduling: Enables scheduling support in your application.<br>
@Scheduled(fixedRate = X): Runs the task at a fixed interval of X milliseconds.<br>
@Scheduled(fixedDelay = X): Runs the task after a delay of X milliseconds from the last completion.<br>
@Scheduled(cron = "expression"): Runs the task based on a cron expression.<br>
@Scheduled(initialDelay = X): Sets an initial delay before the first execution.
