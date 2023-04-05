# Detect iOS WebView

This sample project tries to detect if the page is loaded in iOS WebView (WKWebView, SFSafariViewController and UIWebView)

Tested on iOS 16.

Demo: https://milen-yordanov.github.io/detect-ios-webview/index.html

It uses two methods for iOS WebView detection:

## Method #1
See: https://developer.apple.com/documentation/webkit/wkscriptmessagehandler

window.webkit.messageHandlers is defined in WKWebView with WKScriptMessageHandler

1) if window.webkit.messageHandlers is present then it is 100% WKWebView
3) if window.webkit.messageHandlers is not present then it could be:
   2.1) WKWebView without WKScriptMessageHandler
   2.2) not a WKWebView

## Method #2
It relies on iOS 100vh and 100% sizing calculation.

For 100vh, 100% and `position: fixed` see:

https://developers.google.com/web/updates/2016/12/url-bar-resizing

https://bugs.webkit.org/show_bug.cgi?id=141832

https://github.com/bokand/URLBarSizing
