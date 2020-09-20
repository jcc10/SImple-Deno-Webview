# SImple-Deno-Webview
A simple wrapper for the webview_deno.

# Example

```deno run --unstable -A --refresh https://raw.githubusercontent.com/jcc10/Simple-Deno-Webview/master/demo.ts```

```typescript
import { Application, Context } from "https://deno.land/x/oak/mod.ts";

const app = new Application();

app.use((ctx: Context) => {
  ctx.response.body = "Hello World!";
});

import { SimpleWebView } from "https://raw.githubusercontent.com/jcc10/Simple-Deno-Webview/master/mod.ts";
const test = new SimpleWebView({
  title: "Local webview_deno example",
  url: `http://127.0.0.1:8000/`,
  height: 600,
  resizable: true,
  debug: false,
  frameless: false,
})

app.listen({ port: 8000 });

await test.statusPromise(SimpleWebView.webviewStatus.killed);
Deno.exit();
```