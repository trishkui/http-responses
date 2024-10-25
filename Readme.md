# HTTP response status codes
## 1.Informational responses (100-199)
Informational responses are status codes that indicate the server has received the request and is processing it, but the client should wait for the final response. These codes are temporary and generally don't require any action from the client other than to continue waiting or proceed with additional actions based on the server's instructions
### <u>100 Continue:</u>
 The initial part of the request has been received, and the client should continue sending the rest of the request

 ### <u>101 Switching Protocols:</u>
  The server is switching to a different protocol as requested by the client (e.g., switching from HTTP/1.1 to WebSockets).
  
  ### <u>102 Processing (WebDAV):</u>
  The server has received and is processing the request, but no response is available yet.

  ## 2.Successful Responses (200–299)
  Successful responses indicate that the client's request was received, understood, and processed by the server without any issues. These status codes generally mean that the requested action was successfully carried out, and the result is being returned to the client.

### <u>200 OK: </u>
The request was successful, and the server returned the requested resource or processed the action as expected.
### <u>201 Created: </u>
The request was successful, and a new resource was created as a result. This is often used after a POST request.

### <u>202 Accepted:</u>
The request has been accepted for processing, but the actual processing has not been completed yet.

### <u>204 No Content:</u>
The server successfully processed the request, but there's no content to return. This is often used when a successful DELETE request is made.
 ### <u>205 Reset Content:</u>
 Instructs the client (often a browser) to reset the form or document that sent the request. Commonly used after form submissions.
 ### <u>206 Partial Content:</u>
Sent when the server successfully fulfills a request for part of a resource, such as when the client requests a specific range of data (e.g., downloading part of a file).
 ### <u>207 Multi-Status (WebDAV):</u>
Used to represent multiple status responses for different resources in one message, typically when dealing with collections of files or multiple operations.
 ### <u>208 Already Reported (WebDAV):</u>
 Prevents repeating the listing of internal members of a resource that has already been reported in a previous part of the same response.



 ### <u>226 IM Used (HTTP Delta encoding):</u>
  Indicates that the server applied instance manipulations to the resource before returning it, typically to show the difference between two versions of the resource (e.g., for efficiency in transferring only changes).
  
  ## 3.Redirection messages(300-399):
  Redirection status codes indicate that further action is needed from the client to complete the request. This might involve the client following a different URL or providing additional input.
### <u>300 Multiple Choices:</u>
The server offers multiple possible responses, and the user or client must choose one, but there's no automatic method for this.


  ### <u>301 Moved Permanently:</u>
The requested resource has been permanently moved to a new URL, provided in the response.

  ### <u>302 Found: 300 Multiple Choices:</u>
The resource has temporarily moved to a different URL, but the original URL should still be used for future requests

  ### <u>303 See Other:</u>

The client is directed to retrieve the resource from a different URL using a GET request.

  ### <u>304 Not Modified: </u>
The requested resource has not been modified since the last request, so the client can use its cached version.
  ### <u>305 Use Proxy (Deprecated):</u>
  Previously used to indicate the resource must be accessed via a proxy, but deprecated due to security concerns.

 ### <u>306 Unused: </u>
 Reserved for future use; no longer applicable.

   ### <u>307 Temporary Redirect: </u>
   The client is redirected to another URL, but it must use the same HTTP method as the original request (e.g., POST stays POST).
      
  ### <u>308 Permanent Redirect: </u> 
  The resource is permanently moved to a new URL, and like 307, the HTTP method (e.g., POST) must remain unchanged during redirection.

    
   



## 4.Client error responses

Client error responses (status codes 400–499) indicate issues with the client's request. These errors occur when the request is invalid, unauthorized, or cannot be fulfilled due to some issue with the client’s input or permissions. Common examples include bad syntax, incorrect authentication, or trying to access a resource that doesn’t exist or is restricted

### <u>400 Bad Request:</u>
 The server can't process the request due to client errors (e.g., malformed syntax or invalid framing).

### <u>401 Unauthorized: </u>
The client must authenticate to get the requested response.

### <u>402 Payment Required:
</u>
 Initially for digital payments, but rarely used without a standard convention.

 ### <u>403 Forbidden:</u>
  The client is recognized, but lacks access rights to the resource.

### <u>404 Not Found:</u>
 The requested resource can't be found. Common in browsers when a URL is invalid or missing.

### <u>405 Method Not Allowed:</u>
 The request method is known, but not supported by the resource (e.g., an API may reject a DELETE request).

### <u>406 Not Acceptable:</u>
 No content matches the client’s content negotiation criteria.

### <u>407 Proxy Authentication Required: </u>
Similar to 401, but authentication is needed through a proxy.

### <u>408 Request Timeout: </u>
The server timed out waiting for the client’s request.

### <u>409 Conflict:</u>
 The request conflicts with the current state of the server.

### <u>410 Gone:</u>
 The resource is permanently deleted, with no forwarding address.

### <u>411 Length Required:</u>
 The server requires a Content-Length header, but it wasn't provided.

### <u>412 Precondition Failed:</u>
 Preconditions from the client headers are not met.

### <u>413 Content Too Large:</u>
 The request body exceeds the server’s limit.

### <u>414 URI Too Long:</u> 
The requested URI is too long for the server to handle.

### <u>415 Unsupported Media Type:</u>
 The media format in the request is unsupported.

### <u>416 Range Not Satisfiable:</u>
 The range specified in the request is not valid for the resource.

### <u>417 Expectation Failed:</u>
 The server can't meet the expectations defined in the Expect header.

### <u>418 I’m a Teapot:</u>
 A playful response, meaning the server refuses to brew coffee with a teapot.

### <u>421 Misdirected Request:</u>
 The request was directed to a server that can't fulfill it.

### <u>422 Unprocessable Content (WebDAV): </u>
The request is well-formed, but contains semantic errors.

### <u>423 Locked (WebDAV):</u>
 The requested resource is locked.

### <u>424 Failed Dependency (WebDAV):</u>
 The request failed due to another related request's failure.

### <u>425 Too Early (Experimental):</u> 
The server is unwilling to process the request due to replay risks.

### <u>426 Upgrade Required:</u>
 The client must switch to a different protocol to proceed.

### <u>428 Precondition Required:</u>
 The request must be conditional to prevent conflicts (e.g., lost updates).

### <u>429 Too Many Requests:</u>
 The client has exceeded a rate limit for requests.

### <u>431 Request Header Fields Too Large:</u>
 The request's headers are too large for the server to process.

### <u>451 Unavailable for Legal Reasons:</u>
 The resource is legally restricted (e.g., censored content).

## 5.Server Error Responses(500 – 599)
 indicate that the server encountered an issue preventing it from completing a valid client request. These errors are server-side, meaning they usually result from misconfigurations, unexpected conditions, or temporary unavailability rather than problems with the client’s request. Common examples include the 500 Internal Server Error, 502 Bad Gateway, and 503 Service Unavailable, which inform the client about errors, maintenance, or overload issues. Server errors typically require administrator attention for resolution.
 



 ### <u>500 Internal Server Error: </u>
 A generic error indicating the server encountered an unexpected condition.
### <u>501 Not Implemented: </u>
The server doesn’t support the request method used (except for GET and HEAD).
### <u>502 Bad Gateway: </u>
The server received an invalid response from an upstream server.
### <u>503 Service Unavailable: </u>
The server is temporarily overloaded or under maintenance, often with a “Retry-After” header.
### <u>504 Gateway Timeout: </u>
The server acting as a gateway didn’t receive a timely response from an upstream server.
### <u>505 HTTP Version Not Supported: </u>
The server does not support the HTTP version used in the request.
### <u>506 Variant Also Negotiates:</u> 
A configuration error caused circular references in content negotiation.
### <u>507 Insufficient Storage: </u>
The server lacks storage space to complete the request (specific to WebDAV).
### <u>508 Loop Detected: </u>
An infinite loop was detected during request processing (WebDAV).
### <u>510 Not Extended: </u>
The client’s HTTP extension is unsupported by the server.
### <u>511 Network Authentication Required:</u>
 Network authentication is needed to access the resource.






