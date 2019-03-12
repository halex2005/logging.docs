# Filtering events

**Prerequisites**:

* Install [abstractions module](../modules/abstractions.md)
* Read about general log [configuration practices](../configuration.md)
* Read about [log interface](../concepts/log-interface.md)
* Read about [log events](../concepts/log-events.md)

Filtering allows to select log events recorded by a particular `ILog` instance. Events can be filtered by level, properties or literally any other information present.

### Filter by level

Set a minimum allowed log level \(events of lower levels will be dropped\):

```csharp
log = log.WithMinimumLevel(LogLevel.Warn);
```

Selectively disable some log levels:

```csharp
log = log.WithDisabledLevels(LogLevel.Debug, LogLevel.Fatal);
```



### Filter by properties

Only record events having a property with given name and a of given type value satisfying a predicate:

```csharp
log = log.WithEventsSelectedByProperty<string>("prop", value => value == "foo");
```

Drop events having a property with given name and a value of given type satisfying a predicate:

```csharp
log = log.WithEventsDroppedByProperty<string>("prop", value => value == "foo");
```

Only record events whose properties dictionary satisfies given predicate:

```csharp
log = log.WithEventsSelectedByProperties(props => props.ContainsKey("prop"));
```

Drop events whose properties dictionary satisfies given predicate:

```csharp
log = log.WithEventsDroppedByProperties(props => props.ContainsKey("prop"));
```



### Filter by arbitrary event content

Only record events satisfying given predicate:

```csharp
log = log.SelectEvents(@event => @event.Exception == null);
```

Drop events satisfying given predicate:

```csharp
log.DropEvents(@event => @event.Exception == null);
```
