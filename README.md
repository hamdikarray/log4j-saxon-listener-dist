# log4j-saxon-listener-dist

### Purpose ###

Deal with xsl:message/error/trace XSLT with LOG4J

### Logging  ###

```

<xsl:message select="'hello word'"/>

```

gives this output

> 2022-08-09 09:18:29,575 [pool-2-thread-1] INFO  com.sitc.api.saxon.utils.Log4jMessageListenerProxy  - hello word


```

<xsl:variable name="log" as="xs:element">
  <log level="error" source="com.sitc.xsl.commons.link.xsl">XML error : cannot find the linkid [A1B2C3] target</log>
</xsl:variable>
<xsl:message select="$log"/>

```

gives this output

> 2022-08-09 09:18:29,575 [pool-2-thread-1] ERROR  com.sitc.xsl.commons.link.xsl  - XML error : cannot find the linkid [A1B2C3] target


