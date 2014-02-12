# Spring Security Version Management

If you've ever created a moderately complex project which uses Spring, you've
likely come across issues having to manage versions of Spring transitive
dependencies.

Your project uses Spring Security 3.1.4.RELEASE, but something else you're
depending on imports some otherwise unused Spring Security module, at
3.0.8.RELEASE.

You end up declaring a `dependencyManagement` entry for just about every Spring
Security module there is, to ensure that anything you bring in uses the correct
version.

Enter `spring-security-version`

```xml
<project>
  <dependencyManagement>
    <dependencies>
      <dependency>
        <groupId>com.github.ptomli.spring-security-version</groupId>
        <artifactId>spring-security-version</artifactId>
        <version>3.1.4.RELEASE</version>
        <type>pom</type>
        <scope>import</scope>
      </dependency>
    </dependencies>
  </dependencyManagement>
</project>
```

`spring-security-version` simply declares a `dependencyManagement` entry for
each Spring Security module, at its own `project.version`. So,
`spring-security-version` `3.1.4.RELEASE` will result in any Spring Security
transitive dependency being imported at `3.1.4.RELEASE`. Done, finished and
klaar!

There are companion projects to handle other SpringSource project versions, such
as
[spring-version](https://github.com/ptomli/spring-version)
and
[spring-integration-version](https://github.com/ptomli/spring-integration-version)
