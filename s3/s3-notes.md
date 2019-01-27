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
        - Variable: Value || !Ref ParameterName
``` 