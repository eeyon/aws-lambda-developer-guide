# InvokeAsync<a name="API_InvokeAsync"></a>

**Important**  
This API is deprecated\. We recommend you use `Invoke` API \(see [Invoke](API_Invoke.md)\)\.

Submits an invocation request to AWS Lambda\. Upon receiving the request, Lambda executes the specified function asynchronously\. To see the logs generated by the Lambda function execution, see the CloudWatch Logs console\.

This operation requires permission for the `lambda:InvokeFunction` action\.

## Request Syntax<a name="API_InvokeAsync_RequestSyntax"></a>

```
POST /2014-11-13/functions/FunctionName/invoke-async/ HTTP/1.1

InvokeArgs
```

## URI Request Parameters<a name="API_InvokeAsync_RequestParameters"></a>

The request requires the following URI parameters\.

 ** FunctionName **   
The Lambda function name\. Note that the length constraint applies only to the ARN\. If you specify only the function name, it is limited to 64 characters in length\.  
Length Constraints: Minimum length of 1\. Maximum length of 170\.  
Pattern: `(arn:aws:lambda:)?([a-z]{2}-[a-z]+-\d{1}:)?(\d{12}:)?(function:)?([a-zA-Z0-9-_\.]+)(:(\$LATEST|[a-zA-Z0-9-_]+))?` 

## Request Body<a name="API_InvokeAsync_RequestBody"></a>

The request accepts the following binary data\.

 ** InvokeArgs **   
JSON that you want to provide to your Lambda function as input\.

## Response Syntax<a name="API_InvokeAsync_ResponseSyntax"></a>

```
HTTP/1.1 Status
```

## Response Elements<a name="API_InvokeAsync_ResponseElements"></a>

If the action is successful, the service sends back the following HTTP response\.

 ** Status **   
It will be 202 upon success\.

## Errors<a name="API_InvokeAsync_Errors"></a>

 **InvalidRequestContentException**   
The request body could not be parsed as JSON\.  
HTTP Status Code: 400

 **InvalidRuntimeException**   
The runtime or runtime version specified is not supported\.  
HTTP Status Code: 502

 **ResourceNotFoundException**   
The resource \(for example, a Lambda function or access policy statement\) specified in the request does not exist\.  
HTTP Status Code: 404

 **ServiceException**   
The AWS Lambda service encountered an internal error\.  
HTTP Status Code: 500

## Example<a name="API_InvokeAsync_Examples"></a>

### Invoke a Lambda function<a name="API_InvokeAsync_Example_1"></a>

The following example uses a `POST` request to invoke a Lambda function\. 

#### Sample Request<a name="API_InvokeAsync_Example_1_Request"></a>

```
POST /2014-11-13/functions/helloworld/invoke-async/ HTTP/1.1
[input json]
```

#### Sample Response<a name="API_InvokeAsync_Example_1_Response"></a>

```
HTTP/1.1 202 Accepted
          
x-amzn-requestid: f037bc5c-5a08-11e4-b02e-af446c3f9d0d
content-length: 0
connection: keep-alive
date: Wed, 22 Oct 2014 16:31:55 GMT
content-type: application/json
```

## See Also<a name="API_InvokeAsync_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:

+  [AWS Command Line Interface](http://docs.aws.amazon.com/goto/aws-cli/lambda-2015-03-31/InvokeAsync) 

+  [AWS SDK for \.NET](http://docs.aws.amazon.com/goto/DotNetSDKV3/lambda-2015-03-31/InvokeAsync) 

+  [AWS SDK for C\+\+](http://docs.aws.amazon.com/goto/SdkForCpp/lambda-2015-03-31/InvokeAsync) 

+  [AWS SDK for Go](http://docs.aws.amazon.com/goto/SdkForGoV1/lambda-2015-03-31/InvokeAsync) 

+  [AWS SDK for Java](http://docs.aws.amazon.com/goto/SdkForJava/lambda-2015-03-31/InvokeAsync) 

+  [AWS SDK for JavaScript](http://docs.aws.amazon.com/goto/AWSJavaScriptSDK/lambda-2015-03-31/InvokeAsync) 

+  [AWS SDK for PHP V3](http://docs.aws.amazon.com/goto/SdkForPHPV3/lambda-2015-03-31/InvokeAsync) 

+  [AWS SDK for Python](http://docs.aws.amazon.com/goto/boto3/lambda-2015-03-31/InvokeAsync) 

+  [AWS SDK for Ruby V2](http://docs.aws.amazon.com/goto/SdkForRubyV2/lambda-2015-03-31/InvokeAsync) 