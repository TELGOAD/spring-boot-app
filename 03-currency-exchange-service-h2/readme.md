# Currency Exchange Micro Service

Run com.microservices.currencyconversionservice.CurrencyConversionServiceApplicationH2 as a Java Application.



# Run:

mvn package
Running Container
docker container run --publish 8000:8000 aws-currency-exchange-service-h2:0.0.1-SNAPSHOT
docker run --publish 8000:8000 --network currency-network --name=currency-exchange-service aws-currency-exchange-service-h2:0.0.1-SNAPSHOT

# Test API
### http://localhost:8000/api/currency-exchange-microservice/currency-exchange/from/USD/to/INR

# H2 Console

### http://localhost:8000/api/currency-exchange-microservice/h2-console

Use jdbc:h2:mem:testdb as the JDBC URL.
Tables Created
sql
create table exchange_value 
```json
(
	id bigint not null, 
	conversion_multiple decimal(19,2), 
	currency_from varchar(255), 
	currency_to varchar(255), 
	primary key (id)
)


### http://localhost:8000/api/currency-exchange-microservice/currency-exchange/from/USD/to/INR



{
  "id": 10001,
  "from": "USD",
  "to": "INR",
  "conversionMultiple": 65.00,
  "environmentInfo": "NA"
}




