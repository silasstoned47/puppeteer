<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [puppeteer](./puppeteer.md) &gt; [HTTPRequest](./puppeteer.httprequest.md) &gt; [respond](./puppeteer.httprequest.respond.md)

## HTTPRequest.respond() method

Fulfills a request with the given response.

<b>Signature:</b>

```typescript
respond(response: Partial<ResponseForRequest>, priority?: number): Promise<void>;
```

## Parameters

|  Parameter | Type | Description |
|  --- | --- | --- |
|  response | Partial&lt;[ResponseForRequest](./puppeteer.responseforrequest.md)&gt; | the response to fulfill the request with. |
|  priority | number | If provided, intercept is resolved using cooperative handling rules. Otherwise, intercept is resolved immediately. |

<b>Returns:</b>

Promise&lt;void&gt;

## Remarks

To use this, request interception should be enabled with [Page.setRequestInterception()](./puppeteer.page.setrequestinterception.md).

Exception is immediately thrown if the request interception is not enabled.

## Example

An example of fulfilling all requests with 404 responses:

```js
await page.setRequestInterception(true);
page.on('request', request => {
  request.respond({
    status: 404,
    contentType: 'text/plain',
    body: 'Not Found!'
  });
});

```
NOTE: Mocking responses for dataURL requests is not supported. Calling `request.respond` for a dataURL request is a noop.

