# Spring Security Version Management

SpringSource now manage a _bill of materials_ POM, which targets the same
goals as this project has done historically.

```xml
<project>
  <dependencyManagement>
    <dependencies>
      <dependency>
        <groupId>org.springframework.security</groupId>
        <artifactId>spring-security-bom</artifactId>
        <version>3.2.0.RELEASE</version>
        <type>pom</type>
        <scope>import</scope>
      </dependency>
    </dependencies>
  </dependencyManagement>
</project>
```

I still maintain companion projects to handle other SpringSource project versions, such
as
[spring-version](https://github.com/ptomli/spring-version)
and
[spring-integration-version](https://github.com/ptomli/spring-integration-version).

It is anticipated that SpringSource will produce BOM POMs for these projects, which will
make these projects equally unnecessary going forward.
