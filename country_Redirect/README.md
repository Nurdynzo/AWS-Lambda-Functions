This is a Python code for an AWS Lambda function that generates a redirect response based on the country of the viewer accessing a CloudFront distribution.

The function lambda_handler(event, context) is defined to handle incoming events from a CloudFront distribution. It extracts the request details from the event and retrieves the CloudFront-Viewer-Country header from the request headers.

Based on the value of the CloudFront-Viewer-Country header, the function generates a URL for the country-specific page to redirect the viewer. If the header is not present or has an unrecognized value, the function generates a default URL.

The function constructs a response dictionary with the redirect status code (302) and the location header containing the generated URL. It then returns the response dictionary.

Note that this code requires that the CloudFront distribution is configured to cache based on the CloudFront-Viewer-Country header. Additionally, CloudFront adds the CloudFront-Viewer-Country header after the viewer request event, so this function should be used as a trigger for the origin request event to work properly.