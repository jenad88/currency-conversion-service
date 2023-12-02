# Currency Conversion Micro Service

Run com.johnenad.microservices.currencyconversionservice.CurrencyConversionServiceApplication as a Java Application.

## Containerization

### Troubleshooting

- Problem - Caused by: com.spotify.docker.client.shaded.javax.ws.rs.ProcessingException: java.io.IOException: No such file or directory
- Solution - Check if docker is up and running!
- Problem - Error creating the Docker image on MacOS - java.io.IOException: Cannot run program “docker-credential-osxkeychain”: error=2, No such file or directory
- Solution - https://medium.com/@dakshika/error-creating-the-docker-image-on-macos-wso2-enterprise-integrator-tooling-dfb5b537b44e

### Creating Containers

- mvn package

### Running Containers

```
docker run --publish 8081:8081 --network currency-network --env CURRENCY_EXCHANGE_URI=http://currency-exchange-service:8080 jenad88/aws-currency-conversion-service:0.0.1-SNAPSHOT
```

#### Test API
- http://localhost:8081/api/currency-conversion-service/currency-converter/from/EUR/to/INR/quantity/10
```
docker login
docker push @@@REPO_NAME@@@/aws-currency-conversion-service:0.0.1-SNAPSHOT
```


## Resources

- http://localhost:8081/api/currency-conversion-service/currency-converter/from/EUR/to/INR/quantity/10

```json
{
id: 10002,
from: "EUR",
to: "INR",
conversionMultiple: 75,
quantity: 10,
totalCalculatedAmount: 750,
exchangeEnvironmentInfo: "NA",
conversionEnvironmentInfo: "NA",
}
```