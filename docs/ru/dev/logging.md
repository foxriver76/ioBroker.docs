---
translatedFrom: en
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/dev/logging.md
title: TR: no title
hash: lqS7I0eLZt6tvBnm62QI2XrnTsl3mo5xbcJoPKJRbG8=
---
TR: ## Log Transporter
TR: If you want to subscribe to certain or all logs of ioBroker adapters, you can use **logTransporter**. To activate in your adapter, add `"logTransporter": true` to the common structure of your `io-package.json`.
<br><br> In your adapter code (like in the `main.js` file), you will then need to call `requireLog(true)` to activate.
Once requireLog() is set to true, you can use `on('log', callback)` to subscribe to all new logs coming in from adapters. The callback function returns all logs with the following object (example):

```
{from:'testlog.0', message: 'testlog.0 (12504) adapter disabled', severity: 'error', ts:1585413238439}
```

TR: Full example from a `main.js`:

```
    adapter.requireLog(true);
    adapter.on('log', function(logObject) {
        // Here we have the log in "logObject" and can handle it accordingly.
        const severity = logObject.severity; // the log level (severity): info, warn, error, etc.
        // ....
});
```

TR: ## Background information
TR: There is a special type of adapters, that consume logs. Normally all adapters write their messages into the log file with logger.
But some adapters must to show logs or to store them something else.

TR: To create such a type of adapter it must have **logTransporter** flag in common structure.

TR: If such a flag is present, the adapter.js creates automatically the special state for it - "system.adapter.adapterName.X.logging".
This variable must be set by logTransport adapter to true, when this adapter wants to receive logs.

TR: "system.adapter.adapterName.X.logging" is fifo queue of redis type list.

TR: Other adapters monitor all variables "*.logging" and write into according lists the log messages.
The list is limited by 1000 messages (by default).

TR: The logTransport instance receives the event "log" with message.

TR: To control "system.adapter.adapterName.X.logging" state the adapter must use *requireLog* function.
E.g. ```adapter.requireLog(true);``` to enable receiving of logs.

![TR: Illustration](../../en/dev/media/logging.png)

TR: The functionality is implemented in *adapter.js* and the developer should just set the common flag *logTransporter* and call *requireLog()*.

TR: The functionality for non-logTransport adapters is implemented in *adapter.js* and the developer must not care about it.