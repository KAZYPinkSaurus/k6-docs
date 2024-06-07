---
title: 'Response'
description: 'Browser module: Response Class'
weight: 12
---

# Response

Response represents a response received by the page.

{{< docs/shared source="k6" lookup="browser-module-wip.md" version="<K6_VERSION>" >}}

## Supported APIs

| Method                                                                                                                                                   | Description                                                                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [response.allHeaders()](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/allheaders) {{< docs/bwipt id="965" >}} | Returns an object of headers associated to the response including headers added by the browser.                                                                      |
| [response.body()](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/body)                                         | Returns the response body.                                                                                                                                           |
| [response.frame()](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/frame)                                       | The [Frame](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/frame/) that initiated the request which this response is associated to. |
| [response.headers()](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/headers)                                   | Returns an object of headers associated to the response.                                                                                                             |
| [response.headersArray()](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/headersarray)                         | An array with all the response HTTP headers.                                                                                                                         |
| [response.headerValue(name)](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/headervalue)                       | Returns the value of the header matching the name. The name is case insensitive.                                                                                     |
| [response.headerValues(name)](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/headervalues)                     | Returns all values of the headers matching the name, for example `set-cookie`. The name is case insensitive.                                                         |
| [response.json()](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/json)                                         | Returns the JSON representation of response body.                                                                                                                    |
| [response.ok()](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/ok)                                             | Returns a `boolean` stating whether the response was successful or not.                                                                                              |
| [response.request()](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/request)                                   | Returns the matching [Request](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/request) object.                                      |
| [response.securityDetails()](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/securitydetails)                   | Returns SSL and other security information.                                                                                                                          |
| [response.serverAddr()](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/serveraddr)                             | Returns the IP address and port of the server for this response.                                                                                                     |
| [response.status()](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/status)                                     | Contains the status code of the response (e.g., 200 for a success).                                                                                                  |
| [response.statusText()](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/statustext)                             | Contains the status text of the response (e.g. usually an "OK" for a success).                                                                                       |
| [response.size()](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/size)                                         | The size of the response body and the headers.                                                                                                                       |
| [response.text()](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/text)                                         | Returns the response body as a string.                                                                                                                               |
| [response.url()](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-experimental/browser/response/url)                                           | URL of the response.                                                                                                                                                 |

### Example

{{< code >}}

```javascript
import { browser } from 'k6/experimental/browser';

export const options = {
  scenarios: {
    ui: {
      executor: 'shared-iterations',
      options: {
        browser: {
          type: 'chromium',
        },
      },
    },
  },
};

export default async function () {
  const page = await browser.newPage();

  try {
    // Response returned once goto resolves.
    const res = await page.goto('https://test.k6.io/');
  } finally {
    await page.close();
  }
}
```

{{< /code >}}