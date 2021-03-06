LogglyObjC
==========

This is a simple Objective-C implementation of the Loggly REST API. Here's how to use it:

```objective-c
[Loggly initializeWithCustomerToken:@"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"];
[Loggly logWithLevel:LOG_DEBUG message:@"log message"];
```

You can add tags that log messages will be marked with:

```objective-c
[Loggly.tags addObject:@"tag_name"];
```

Log messages will be sent in JSON format with predefined fields for the message, log level and timestamp. You can add custom fields to the JSON body:

```objective-c
[Loggly.fields setObject:@"value" forKey:@"key"];
```

Log messages are sent immediately if a network connection is available. If not, they are queued up (with the timestamp recorded) and sent every 5 minutes.
