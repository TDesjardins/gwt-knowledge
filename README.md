# GWT Knowledge
Collection of GWT knowledge and resources


## GWT 3

### Module Migration

* [Common info about GWT module migration](https://github.com/Vertispan/some-gwt-module)
* [GWT Module migration guide](https://github.com/FrankHossfeld/gwt-modules-migration)
* [GWT-Modules release checklist](https://docs.google.com/document/d/1fTRTSMA_Nsmiam9YUSrVlQQL02C6YGjWw5QRn6NpdCQ/)
* [List of module migration state](https://docs.google.com/spreadsheets/d/1b1D9fEqRh5lZ8cqMJtYoc_25rfTRvsuJkTtS2vjgi3o/)
* [List of module migration progress](https://docs.google.com/spreadsheets/d/15WXfiklnTeqjRLI8gKj5iyGk7iDhnuQHGcpYJgpNlmQ/)

## J2CL

### J2CL Maven Plugin

#### Source code
https://github.com/Vertispan/j2clmavenplugin

#### Repo
https://repo.vertispan.com/j2cl/com/vertispan/j2cl/j2cl-maven-plugin/

#### Configuration
```xml
<plugin>
  <groupId>com.vertispan.j2cl</groupId>
    <artifactId>j2cl-maven-plugin</artifactId>
    <version>0.13-SNAPSHOT</version>
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

#### Entrypoint

```MyEntryPoint.native.js```
```javascript
setTimeout(function(){
  // Call the java "constructor" method, `new` will only work if it is a @JsType, or maybe
  // once optimized. Without this, in BUNDLE mode, `new` doesn't include the clinit, so
  // static imports haven't been resolved yet.
  var ep = MyEntryPoint.$create__();
  // Invoke onModuleLoad to start the app.
  ep.m_onModuleLoad__()
}, 0);
```

## JsInterop

* [JsInterop specification v1.0](https://docs.google.com/document/d/10fmlEYIHcyead_4R1S5wKGs1t2I7Fnp_PaNaa7XTEk0/edit#heading=h.o7amqk9edhb9)
* [jsinterop-base (Utilities for GWT and J2CL to interact with JavaScript beyond JsInterop)](https://github.com/google/jsinterop-base)
* [Elemental2 (Type checked access to browser APIs for Java code)](https://github.com/google/elemental2)
* [JsInterop knowledge from VueGWT site](https://vuegwt.github.io/vue-gwt/guide/gwt-integration/js-interop.html)
* [Nice short introduction to JsInterop](http://www.luigibifulco.it/blog/en/blog/gwt-2-8-0-jsinterop)

## Miscellaneous
* [Reduce compile time (also relevant for non gxt projects)](https://www.sencha.com/blog/how-to-reduce-compilation-time-for-your-gxt-projects/)
* [Curated list of GWT related news, links, blogs and libraries (by awesomegwt)](https://gwt.zeef.com/awesomegwt)
* [Modern GWT, first steps](https://dev.to/ibaca/modern-gwt-first-steps-509k)
