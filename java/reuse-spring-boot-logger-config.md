# Reuse Spring Boot log config

Sometimes what you just want to do is add more specific rules to your logger, o define e different root log level.
You can leverage Spring boot to help you with this including the spring-boot base.xml file into your logger.xml file

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
    <include resource="org/springframework/boot/logging/logback/base.xml"/>
    <!-- Your specific configuration -->
</configuration>
```