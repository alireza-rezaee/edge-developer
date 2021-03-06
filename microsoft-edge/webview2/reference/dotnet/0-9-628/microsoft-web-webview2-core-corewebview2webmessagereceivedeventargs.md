---
description: Embed web technologies (HTML, CSS, and JavaScript) in your native applications with the Microsoft Edge WebView2 control
title: Microsoft.Web.WebView2.Core.CoreWebView2WebMessageReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: Microsoft.Web.WebView2, Core, webview2, webview, dotnet, wpf, winforms, app, edge, CoreWebView2, CoreWebView2Controller, browser control, edge html, Microsoft.Web.WebView2.Core.CoreWebView2WebMessageReceivedEventArgs
---

# Microsoft.Web.WebView2.Core.CoreWebView2WebMessageReceivedEventArgs class 

Namespace: Microsoft.Web.WebView2.Core\
Assembly: Microsoft.Web.WebView2.Core.dll

Event args for the WebMessageReceived event.

## Summary

 Members                        | Descriptions
--------------------------------|---------------------------------------------
[Source](#source) | The URI of the document that sent this web message.
[WebMessageAsJson](#webmessageasjson) | The message posted from the WebView content to the host converted to a JSON string.
[TryGetWebMessageAsString](#trygetwebmessageasstring) | If the message posted from the WebView content to the host is a string type, this method will return the value of that string.

## Members

#### Source 

The URI of the document that sent this web message.

> public string [Source](#source)

#### WebMessageAsJson 

The message posted from the WebView content to the host converted to a JSON string.

> public string [WebMessageAsJson](#webmessageasjson)

Use this to communicate via JavaScript objects.

For example the following postMessage calls result in the following WebMessageAsJson values:

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### TryGetWebMessageAsString 

If the message posted from the WebView content to the host is a string type, this method will return the value of that string.

> public string [TryGetWebMessageAsString](#trygetwebmessageasstring)()

If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG. Use this to communicate via simple strings.

For example the following postMessage calls result in the following WebMessageAsString values:

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

