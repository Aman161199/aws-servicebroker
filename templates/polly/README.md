# AWS Service Broker - Amazon Polly Documentation

<img  align="left" src="https://s3.amazonaws.com/awsservicebroker/icons/aws-service-broker.png" width="120"><img align="right" src="https://s3.amazonaws.com/awsservicebroker/icons/AmazonPolly_LARGE.png" width="108"> <p align="center">Amazon Polly is a Text-to-Speech (TTS) cloud service that converts text into lifelike speech. You can use Amazon Polly to develop applications that increase engagement and accessibility. Amazon Polly supports multiple languages and includes a variety of lifelike voices, so you can build speech-enabled applications that work in multiple locations and use the ideal voice for your customers.
https://aws.amazon.com/documentation/polly/</p>

Table of contents
=================

* [Parameters](#parameters)
  * [default](#param-default)
* [Bind Credentials](#bind-credentials)
* [Examples](#kubernetes-openshift-examples)
  * [default](#example-default)

<a id="parameters" />

# Parameters

<a id="param-default" />

## default

Enables use of AWS Polly Speech Synthesis

Pricing: https://aws.amazon.com/polly/pricing/

### Required

At a minimum these parameters must be declared when provisioning an instance of this service

Name           | Description     | Accepted Values
-------------- | --------------- | ---------------
LexiconPrefix|Restrict the use of Polly lexicons to those with the specified prefix. If left blank all lexicons can be managed. The restriction applies to the SynthesizeSpeech, GetLexicon, PutLexicon and DeleteLexicon API's|string


### Generic

These parameters are required, but generic or require privileged access to the underlying AWS account, we recommend they are configured with a broker secret, see [broker documentation](/docs/) for details.

Name           | Description     | Default         | Accepted Values
-------------- | --------------- | --------------- | ---------------
target_account_id|AWS Account ID to provision into (optional)||
target_role_name|IAM Role name to provision with (optional), must be used in combination with target_account_id||
region|AWS Region to create RDS instance in.|us-west-2|ap-northeast-1, ap-northeast-2, ap-south-1, ap-southeast-1, ap-southeast-2, ca-central-1, eu-central-1, eu-west-1, eu-west-2, sa-east-1, us-east-1, us-east-2, us-west-1, us-west-2

<a id="bind-credentials" />

# Bind Credentials

These are the environment variables that are available to an application on bind.

Name           | Description
-------------- | ---------------

<a id="kubernetes-openshift-examples" />

# Kubernetes/Openshift Examples

***Note:*** Examples do not include generic parameters, if you have not setup defaults for these you will need to add
them as additional parameters

<a id="example-default" />

## default

### Minimal
```yaml
apiVersion: servicecatalog.k8s.io/v1beta1
kind: ServiceInstance
metadata:
  name: polly-default-minimal-example
spec:
  clusterServiceClassExternalName: polly
  clusterServicePlanExternalName: default
  parameters:
    LexiconPrefix: [VALUE] # REQUIRED
```

### Complete
```yaml
apiVersion: servicecatalog.k8s.io/v1beta1
kind: ServiceInstance
metadata:
  name: polly-default-complete-example
spec:
  clusterServiceClassExternalName: polly
  clusterServicePlanExternalName: default
  parameters:
    LexiconPrefix: [VALUE] # REQUIRED
```

