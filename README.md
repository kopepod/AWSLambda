# AWSLambda

This tutorial shows how to create a API with python backbone, steps:
1. Create a Lambda function
2. Create an API gateway
3. Test using curl

## Lambda Function
1. Login https://us-east-1.console.aws.amazon.com/console/
2. Search Lambda
3. Create function
4. Select Author from scratch
5. Give funcion name, e.g., myfunction
6. Select Runtime python 3.8
7. Leave the rest and click on create Function

8. Edit _lambda_function.py_ as
```
# lambda_function.py
import json


def lambda_handler(event, context):
    Body = event.get('body')
    Body = json.loads(Body)
    Time = Body.get('time')
    return {
        'statusCode': 200,
        'body': json.dumps('Hello you ! %s' %(Time) )
    }
```

## API gateway
1. Login https://us-east-1.console.aws.amazon.com/console/
2. Search API gateway
3. Click on Create API
4. Select HTTP API and click Build
