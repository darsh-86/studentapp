## Creating Kubernetes Secrets

To create a secret in Kubernetes, use the following command:
```sh
kubectl create secret generic db-secret --from-literal=username=root --from-literal=password=darsh@4321
```

## Running a Docker Container from an Image

To create and run a container from an image, use this command:
```sh
docker run -d --name test-container -e DB_USERNAME=root -e DB_PASSWORD=darsh@4321 your-image-name:your-tag
```

## Retrieving Kubernetes Secrets

To retrieve the secret in YAML format:
```sh
kubectl get secret db-secret -o yaml
```

The output will look something like this:
```yaml
apiVersion: v1
data:
  password: ZGFyc2hANDMyMQ==
  username: cm9vdA==
kind: Secret
metadata:
  name: db-secret
  namespace: default
type: Opaque
```

To decode the username:
```sh
echo 'cm9vdA==' | base64 --decode
```

To decode the password:
```sh
echo 'ZGFyc2hANDMyMQ==' | base64 --decode
```

## Building a MySQL Student Database Image

To build a MySQL student database image, use the following commands:

```sh
docker buildx build --platform linux/amd64 -t your-mysql-image:latest --build-arg MYSQL_ROOT_PASSWORD=rootpassword --build-arg MYSQL_DATABASE=studentapp .

docker buildx build --platform linux/amd64 -t studentdb:latest --build-arg MYSQL_ROOT_PASSWORD=$(kubectl get secret db-secret -o=jsonpath='{.data.password}' | base64 --decode) --build-arg MYSQL_DATABASE=$(kubectl get secret db-secret -o=jsonpath='{.data.username}' | base64 --decode) --load .
```

## Running the MySQL Container

To run the MySQL container:
```sh
docker run -d --name test-mysql-container -e MYSQL_ROOT_PASSWORD=rootpassword -e MYSQL_DATABASE=studentapp studentdb:latest

docker run -d --name test-mysql-container -e MYSQL_ROOT_PASSWORD=$(kubectl get secret db-secret -o=jsonpath='{.data.password}' | base64 --decode) -e MYSQL_DATABASE=$(kubectl get secret db-secret -o=jsonpath='{.data.username}' | base64 --decode) studentdb:latest
```
