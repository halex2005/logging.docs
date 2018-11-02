---
description: 'http://vostok.tools'
---

# Home

## Vostok.Logging

Logging is a means of tracking events that occur during the operation of some processes.  
Vostok.Logging like other libraries provides diagnostic logging to files, the console, and elsewhere.

## Libraries

Vostok.Logging is a set of libraries. 

### Logging.Abstractions

This library is a facade with core logging interfaces and models \([ILog](basics.md#ilog), [LogEvent](basics.md#logevent), [LogLevel](basics.md#loglevel)\) and a set of useful extensions.

### Logging.Console

This library is for a log which outputs events to console. Supports color-marked messages, uses lock-free queue for asynchronous message writing.

### Logging.File

This library is for a log which outputs events to file. Supports rolling-strategies for logs rotation, uses lock-free queue for asynchronous message writing, easy to configure from code and other sources.

### Logging.Context

Automatically adds info to log messages from background context.

### Logging.Formatting

Rendering messages and events to document. Can be used in your realisations of text logging.

### [Logging.Log4Net](integration-with-serilog-log4net/)

Represents an adapter between Vostok logging interfaces and log4net.

### [Logging.Serilog](integration-with-serilog-log4net/)

Represents an adapter between Vostok logging interfaces and Serilog.

### Logging.Hercules

## Features:

* **Structured logging** Log event consists of a timestamp, a log message, a saved exception and user-defined properties. 
* **Fully asynchronous** 
* **Flexible setting** 
* **Fast work** 
* \*\*\*\*[**Integration with Serilog and Log4Net**](integration-with-serilog-log4net/) ****You can try Vostok right now. No need to translate the whole system to the Vostok at once. Just use an adapter. 

But Vostok is not just one library it's a toolbox. If you use several Vostok libraries, your profit is in good integration.  
No worries about compatibility and other libraries.



