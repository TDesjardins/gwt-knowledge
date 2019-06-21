# GWT Knowledge
Collection of GWT knowledge and resources


## GWT 3

### Module Migration

[How to migrate a GWT module](https://github.com/Vertispan/some-gwt-module)

[List of module migration state](https://docs.google.com/spreadsheets/d/1b1D9fEqRh5lZ8cqMJtYoc_25rfTRvsuJkTtS2vjgi3o/edit#gid=0)

## J2CL

### J2CL Maven Plugin

#### Repo
https://repo.vertispan.com/j2cl/com/vertispan/j2cl/j2cl-maven-plugin/

#### Configuration
```xml
<plugin>
  <groupId>com.vertispan.j2cl</groupId>
    <artifactId>j2cl-maven-plugin</artifactId>
    <version>0.1-SNAPSHOT</version>
    <executions>
      <execution>
        <id>build-js</id>
        <phase>process-classes</phase>
          <goals>
            <goal>build</goal>
          </goals>
        </execution>
    </executions>
    <configuration>
      <entrypoint>com.example.my.EntryPoint</entrypoint>
    </configuration>
</plugin>
```
