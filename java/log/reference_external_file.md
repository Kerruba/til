# How to reference an external file in your logback.xml configuration
Sometimes is useful to reference variables from an external file,
happened to me when I wanted to customize the logs name and path.

You can reference an external file in your configuration using
```xml
<property file="path/to/the/file.properties" />
```

or use a resource file present in your class path
```xml
<property resource="resource.properties" />
```

The external resource/files should contain variables in the format
```
<VARIABLE_NAME>=<VARIABLE_VALUE>
```
and you can reference such variables using `${VARIABLE_NAME}` in your logback.xml file