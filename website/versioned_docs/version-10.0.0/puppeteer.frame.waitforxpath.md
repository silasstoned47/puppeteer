<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [puppeteer](./puppeteer.md) &gt; [Frame](./puppeteer.frame.md) &gt; [waitForXPath](./puppeteer.frame.waitforxpath.md)

## Frame.waitForXPath() method

<b>Signature:</b>

```typescript
waitForXPath(xpath: string, options?: WaitForSelectorOptions): Promise<ElementHandle | null>;
```

## Parameters

|  Parameter | Type | Description |
|  --- | --- | --- |
|  xpath | string | the XPath expression to wait for. |
|  options | [WaitForSelectorOptions](./puppeteer.waitforselectoroptions.md) | options to configure the visiblity of the element and how long to wait before timing out. |

<b>Returns:</b>

Promise&lt;[ElementHandle](./puppeteer.elementhandle.md) \| null&gt;

## Remarks

Wait for the `xpath` to appear in page. If at the moment of calling the method the `xpath` already exists, the method will return immediately. If the xpath doesn't appear after the `timeout` milliseconds of waiting, the function will throw.

For a code example, see the example for [Frame.waitForSelector()](./puppeteer.frame.waitforselector.md). That function behaves identically other than taking a CSS selector rather than an XPath.

