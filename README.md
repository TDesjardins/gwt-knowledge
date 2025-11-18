# GWT Knowledge
Collection of GWT knowledge and resources


## GWT 3

### Modules

#### Module Migration

* [Common info about GWT module migration](https://github.com/Vertispan/some-gwt-module)
* [GWT Module migration guide](https://github.com/FrankHossfeld/gwt-modules-migration)
* [GWT-Modules release checklist](https://docs.google.com/document/d/1fTRTSMA_Nsmiam9YUSrVlQQL02C6YGjWw5QRn6NpdCQ/)
* [List of module migration state](https://docs.google.com/spreadsheets/d/1b1D9fEqRh5lZ8cqMJtYoc_25rfTRvsuJkTtS2vjgi3o/)
* [List of module migration progress](https://docs.google.com/spreadsheets/d/15WXfiklnTeqjRLI8gKj5iyGk7iDhnuQHGcpYJgpNlmQ/)

#### Resources

* [Bill of Materials (BOM)](https://github.com/FrankHossfeld/gwt-modules)

## J2CL

### J2CL Maven Plugin
![Maven Central](https://img.shields.io/maven-central/v/com.vertispan.j2cl/j2cl-maven-plugin.svg?colorB=44cc11)

#### Source code
https://github.com/Vertispan/j2clmavenplugin

#### Repo
https://repo.vertispan.com/j2cl/com/vertispan/j2cl/j2cl-maven-plugin/

#### Configuration
```xml
<plugin>
  <groupId>com.vertispan.j2cl</groupId>
    <artifactId>j2cl-maven-plugin</artifactId>
    <version>0.16-SNAPSHOT</version>
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

### Links

* [RISE OF J2CL: JAVA WEB DEVELOPMENT AFTER GWT](https://blog.kie.org/2022/04/rise-of-j2cl-java-web-development-after-gwt.html)
* [Java for web frontend developers, part 1 (Dmitrii Tikhomirov)](https://dev.to/treblereel/java-for-web-frontend-developers-part-1-generating-a-simple-project-41jp)
* [Java for web frontend developers, part 2 (Dmitrii Tikhomirov)](https://dev.to/treblereel/java-for-web-frontend-developers-part-2-getting-started-with-j2cl-314g)
* [Reverse-engineering J2CL–Bazel integration](https://blog.ltgt.net/reverse-engineering-j2cl-bazel-integration/)
* [Designing a Gradle plugin for J2CL](https://dev.to/tbroyer/designing-a-gradle-plugin-for-j2cl-c7k)
* [Deploy GWT / J2CL Web Apps on Azure Static Web Apps Service](https://medium.com/geekculture/deploy-gwt-j2cl-web-apps-on-azure-static-web-apps-service-effddb6f4047)
* [GraalVM + WASM from the Perspective of a J2CL/GWT Developer](https://dev.to/treblereel/graalvm-wasm-from-the-perspective-of-a-j2clgwt-developer-4i)

## JsInterop

* [JsInterop specification v1.0](https://docs.google.com/document/d/10fmlEYIHcyead_4R1S5wKGs1t2I7Fnp_PaNaa7XTEk0/edit#heading=h.o7amqk9edhb9)
* [jsinterop-base (Utilities for GWT and J2CL to interact with JavaScript beyond JsInterop)](https://github.com/google/jsinterop-base)
* [JsInterop knowledge from VueGWT site](https://vuegwt.github.io/vue-gwt/guide/gwt-integration/js-interop.html)
* [Nice short introduction to JsInterop](https://web.archive.org/web/20200712185409/http://www.luigibifulco.it/blog/en/blog/gwt-2-8-0-jsinterop)

## Elemental2
* [Javadoc](https://javadoc.io/doc/com.google.elemental2/elemental2-dom/latest/elemental2/dom/package-summary.html)
* [Elemental2 (Type checked access to browser APIs for Java code)](https://github.com/google/elemental2)
* [File DnD Example (by Brandon Donnelson)](https://gist.github.com/branflake2267/8f99301a21944f54ca76b556e4a32a9d)
* [Canvas and 2D Context use(by Brandon Donnelson)](https://gist.github.com/branflake2267/8e4b9d4f2dc594fe21a125155516ec97)

## Miscellaneous
* [Reduce compile time (also relevant for non gxt projects)](https://www.sencha.com/blog/how-to-reduce-compilation-time-for-your-gxt-projects/)
* [Curated list of GWT related news, links, blogs and libraries (by awesomegwt)](https://gwt.zeef.com/awesomegwt)
* [Modern GWT, first steps (article by Ignacio Baca Moreno-Torres)](https://dev.to/ibaca/modern-gwt-first-steps-509k)
* [Modern GWT, Introduction (slides from Dr. Lofi Dewanto)](https://docs.google.com/presentation/d/1cr-rYGz58ngC6sgOy8c7oErhaj0VdLUHk9Y5mcvgrP0/edit#slide=id.p)
* [Modern GWT / J2CL Transpiler for Dummies (padlet from Dr. Lofi Dewanto)](https://padlet.com/lofidewanto/gwtintro)
* [5 Pillars of a Successful Java Web Application](https://medium.com/kie-foundation/5-pillars-of-a-successful-java-web-application-57f7632d1562)
* [Using webworkers in GWT](https://gitlab.com/ManfredTremmel/gwt-webworker)
* [GWT emulation classes (source code)](https://github.com/gwtproject/gwt/tree/master/user/super/com/google/gwt/emul)
* [Dynamite Duo: GWT Boot and Spring Boot (article by Dr. Lofi Dewanto)](https://medium.com/geekculture/dynamite-duo-gwt-boot-and-spring-boot-e5a966782344)
* [Three.js for Java devs: J2CL, Closure, Bazel, etc ...](https://dev.to/treblereel/threejs-for-java-devs-j2cl-closure-bazel-etc--28kc)
* [GWT.create 2015 - Disassembling Compiled GWT Sources (Colin Alworth)](https://www.youtube.com/watch?app=desktop&v=dE5Zz8YQdgM)
