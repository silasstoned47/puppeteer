<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [puppeteer](./puppeteer.md) &gt; [ElementHandle](./puppeteer.elementhandle.md) &gt; [$$eval](./puppeteer.elementhandle.__eval.md)

## ElementHandle.$$eval() method

This method runs `document.querySelectorAll` within the element and passes it as the first argument to `pageFunction`. If there's no element matching `selector`, the method throws an error.

If `pageFunction` returns a Promise, then `frame.$$eval` would wait for the promise to resolve and return its value.

<b>Signature:</b>

```typescript
$$eval<ReturnType>(selector: string, pageFunction: (elements: Element[], ...args: unknown[]) => ReturnType | Promise<ReturnType>, ...args: SerializableOrJSHandle[]): Promise<WrapElementHandle<ReturnType>>;
```

## Parameters

|  Parameter | Type | Description |
|  --- | --- | --- |
|  selector | string |  |
|  pageFunction | (elements: Element\[\], ...args: unknown\[\]) =&gt; ReturnType \| Promise&lt;ReturnType&gt; |  |
|  args | [SerializableOrJSHandle](./puppeteer.serializableorjshandle.md)\[\] |  |

<b>Returns:</b>

Promise&lt;[WrapElementHandle](./puppeteer.wrapelementhandle.md)&lt;ReturnType&gt;&gt;

## Example 1


```html
<div class="feed">
  <div class="tweet">Hello!</div>
  <div class="tweet">Hi!</div>
</div>

```

## Example 2


```js
const feedHandle = await page.$('.feed');
expect(await feedHandle.$$eval('.tweet', nodes => nodes.map(n => n.innerText)))
 .toEqual(['Hello!', 'Hi!']);

```

