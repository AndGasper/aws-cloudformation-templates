# `static-website.yaml`
- Makes reference to a parameter for the domain name

Mostly because I forget the commands:

## How to put the templates up into the cloud
Example:
```
aws s3 cp ./s3/static-website.yaml s3://cloudformation-templates-modular/s3/
```
(--recursive to do a whole folder)
General form 
```
aws s3 /path/to/file s3://{bucketName}/file/path 
```


Hmm...


```
Properties:
    Attribute: !Sub
        - ${VariableName}
        - VariableName: Value || !Ref ParameterName
``` 

Save yourself some heartache and make sure the bucket created is actually associated with something you can read. 

The first go around, I forgot the:
```
Properties
    BucketName: !Sub
        - ${Domain}
        - Domain: !Ref RootDomainName
```
and I didn't want to deal with copying everything over, but I'm getting an unintended detour through the Route53 record set stuff. 

:triumph: 