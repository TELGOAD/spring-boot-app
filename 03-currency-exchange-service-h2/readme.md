Currency Exchange Micro Service - H2
Run com.microservices.currencyconversionservice.CurrencyConversionServiceApplicationH2 as a Java Application.

Containerization
Troubleshooting
Problem: Caused by: com.spotify.docker.client.shaded.javax.ws.rs.ProcessingException: java.io.IOException: No such file or directory
Solution: Check if Docker is up and running!

Problem: Error creating the Docker image on MacOS - java.io.IOException: Cannot run program “docker-credential-osxkeychain”: error=2, No such file or directory
Solution: See this article

Creating Container
Run:

bash
Copy
Edit
mvn package
Running Container
docker container run --publish 8000:8000 aws-currency-exchange-service-h2:0.0.1-SNAPSHOT
docker run --publish 8000:8000 --network currency-network --name=currency-exchange-service aws-currency-exchange-service-h2:0.0.1-SNAPSHOT
Test API
http://localhost:8000/api/currency-exchange-microservice/currency-exchange/from/USD/to/INR
docker login
docker push @@@REPO_NAME@@@/aws-currency-exchange-service-h2:0.0.1-SNAPSHOT
Resources
http://localhost:8000/api/currency-exchange-microservice/currency-exchange/from/USD/to/INR
{
  "id": 10001,
  "from": "USD",
  "to": "INR",
  "conversionMultiple": 65.00,
  "environmentInfo": "NA"
}
H2 Console
http://localhost:8000/api/currency-exchange-microservice/h2-console
Use jdbc:h2:mem:testdb as the JDBC URL.
Tables Created
sql
create table exchange_value 
(
	id bigint not null, 
	conversion_multiple decimal(19,2), 
	currency_from varchar(255), 
	currency_to varchar(255), 
	primary key (id)
)