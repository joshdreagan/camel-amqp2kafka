# camel-amqp2kafka

## Requirements

- [Apache Maven 3.x](http://maven.apache.org)

## Preparing

```
cd $PROJECT_ROOT
mvn clean install
```

## Running the example standalone

```
cd $PROJECT_ROOT
mvn spring-boot:run
```

## Running the example in OpenShift

```
oc new-project demo
oc create -f src/main/kube/serviceaccount.yml
oc create -f src/main/kube/configmap.yml
oc create -f src/main/kube/secret.yml
oc secrets add sa/camel-amqp2kafka-sa secret/camel-amqp2kafka-secret
oc policy add-role-to-user view system:serviceaccount:demo:camel-amqp2kafka-sa
mvn -P openshift clean install fabric8:deploy
```

## Testing the code
