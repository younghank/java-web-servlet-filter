[![Build Status][ci-img]][ci] [![Released Version][maven-img]][maven]

# OpenTracing Java Web Servlet Filter Instrumentation

This library provides instrumentation for Java Web Servlet applications.

## Initialization

Tracing filter can be programmatically initialized:
```java
   TracingFilter filter = new TracingFilter(tracer);
   servletContext.addFilter("tracingFilter", filter);
```

or added to `web.xml`, however it requires to register a tracer instance: `GlobalTracer.register(tracer)`.

## Accessing Server Span
Current server span context is accessible in HttpServletRequest attributes.
```java
   SpanContext spanContext = (SpanContext)httpservletRequest.getAttribute(TracingFilter.SERVER_SPAN_CONTEXT);
   
```

## Development
```shell
./mvnw clean install
```

## Release
Follow instructions in [RELEASE](RELEASE.md)


   [ci-img]: https://travis-ci.org/opentracing-contrib/java-web-servlet-filter.svg?branch=master
   [ci]: https://travis-ci.org/opentracing-contrib/java-web-servlet-filter
   [maven-img]: https://img.shields.io/maven-central/v/io.opentracing.contrib/opentracing-web-servlet-filter.svg?maxAge=2592000
   [maven]: http://search.maven.org/#search%7Cga%7C1%7Copentracing-web-servlet-filter
