---
title: remote-service
layout: default
---

The `remote-service` module is used by [AFS]() to define a remote AFS server.

Read the [documentation]() page to learn more about the remote AFS server implementation.

# Properties

## Required properties

## host-name

The `host-name` property is a required property that defines the name of the remote host.

## app-name

The `app-name` property is a required property that defines the name of the remote application server.

## Optional properties

## secure

The `secure` property is an optional property that defines if SSL/TLS protocol should be used
to connect to the remote server. The default value of this property is `true`.

## port

The `port` property is an optional property that defines the connection port. By default, if SSL/TLS protocol
is used, the default value of this property is `443`. Otherwise, it is `80`.

## autoreconnectEnabled

The `autoreconnectEnabled` property is an optional property that defines if auto reconnection to the server should be used when to disconnect. The default value of this property is `false`.

## reconnectionInitialInterval

The `reconnectionInitialInterval` property is an optional property that defines the reconnection initial interval. The default value of this property is `5`in seconds.

## reconnectionIntervalMutiplier

The `reconnectionIntervalMutiplier` property is an optional property that defines the reconnection interval mutiplier. The default value of this property is `2`.

## reconnectionMaxInterval

The `reconnectionMaxInterval` property is an optional property that defines the max interval between two reconnection. The default value of this property is `3600`in seconds.
With the default parameters, there would be no reconnection attempt.
With autoreconnect set to true and the other parameters set to default values, in the case of a disconnection, the reconnection attempts would occur after 5", then 10", 20", 40", 1'20", 2'40" .... etc incresing until a maximum of one hour interval. after reconnection max intenal, the reconnection will be re-attempted every hour.

## reconnectionMax

The `reconnectionMax` property is an optional property that defines the maximum time before abandoning reconnection. The default value of this property is the maximum value for an int, in seconds.
   
# Examples

## YAML
```yaml
remote-service:
    host-name: my-afs-server
    app-name: my-server-app
    secure: false
    port: 8080
    autoreconnect-enabled: false
    reconnection-initial-interval: 5
    reconnection-interval-mutiplier: 2
    reconnection-max-interval: 3600
    reconnection-max: 2147483647
```

## XML
```xml
<remote-service>
    <host-name>my-afs-server</host-name>
    <app-name>my-server-app</app-name>
    <secure>false</secure>
    <port>8080</port>
    <autoreconnect-enabled>: false</autoreconnect-enabled>
    <reconnection-initial-interval>5</reconnection-initial-interval>
    <reconnection-interval-mutiplier>2</reconnection-interval-mutiplier>
    <reconnection-max-interval>3600</reconnection-max-interval>
    <reconnection-max>2147483647 </reconnection-max>
</remote-service>
```
