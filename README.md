# tinylog-simplemail-and-masked-writer
## Overview
This is a set of [custom writer](https://tinylog.org/v2/extending/#custom-writer) for [tinylog 2](https://tinylog.org/v2/) logging framework.

## Installation
Maven
```
<dependency>
    <groupId>com.github.schelldorfer</groupId>
    <artifactId>tinylog-simplemail-and-masked-writer</artifactId>
    <version>1.0.0</version>
</dependency>
```
Build Respository: https://artifactory.e-switch.ch/artifactory/libs-release-public

## SimpleMailWriter
Email Writer based on Simple Java Mail

Emails are sent with [Simple Java Mail](https://www.simplejavamail.org/) which is based on Jakarata Mail 2 library.

### Configuration

#### Writer name
`simple mail`

#### Mail configuration
set mail properties directly in tinylog configuration writer config

see https://www.simplejavamail.org/configuration.html#section-available-properties for all available properties

#### Message Formatter
[Message Formatter](https://tinylog.org/v2/extending/#custom-logging-api) (`format` property) is supported

#### Example
example of `tinylog.properties`:
```
writer_simplemail=simple mail
writer_simplemail.level=error
writer_simplemail.format={date: yyyy-MM-dd HH:mm:ss.SSS} {{level}|min-size=7} [{thread}] {class}.{method}()\t{context: prefix}{message}
writer_simplemail.simplejavamail.javaxmail.debug=false
writer_simplemail.simplejavamail.smtp.host=smtp.mailserver.com
writer_simplemail.simplejavamail.defaults.subject=SimpleMail Writer
writer_simplemail.simplejavamail.defaults.from.address=simplemail@mailserver.com
writer_simplemail.simplejavamail.defaults.to.address=help@mailserver.com
```

## Masked Writers
Masked Writers allow to mask (replace) some part of the log message.

### Configuration

#### Writer names
`masked console`, `masked file` and  `masked rolling file`

see [MaskedWriterUtil](src/main/java/com/github/schelldorfer/tinylog/writers/MaskedWriterUtil.java) for description, configuration and usage






