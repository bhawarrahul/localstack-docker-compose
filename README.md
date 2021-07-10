# localstack-docker-compose
localstack-docker-compose 

# start local stack docker
````
-> docker-compose up
````

# Secret Create
#### Note- ```` Install AWS CLI before use below commands ````
### Create binary secret - Binary secret support in AWS CLI only(AWS console not support binary secret create - https://docs.aws.amazon.com/secretsmanager/latest/apireference/API_PutSecretValue.html)
````aws --endpoint-url=http://localhost:4566 secretsmanager create-secret --name <secret-name> --description <description> --secret-binary fileb://<file-path-with-extension>````
- Binary secret file have size limit, please check AWS documents
- Generally, Binary secret used to store certificate files(.cer,.jks, .key etc).

### Create String type secret using json file
````aws --endpoint-url=http://localhost:4566 secretsmanager  create-secret --name <secret-name> --description <description> --secret-string file://<json-file-path-with-extension>````

### JSON file sample
````
{
	"Secret-key1": "Secret-value1",
	"Secret-key2": "Secret-value2",
	 .
	 .
	 .
	"Secret-key-N": "Secret-value-N"
}
````
