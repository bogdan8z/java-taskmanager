# Do a simple project (compare .net to java)
## Step 1: Create project in git

## Step 2: Create your first Spring Boot API

- Go to Spring Initializr.
- Configure:

```text
Project:       Maven
Language:      Java
Spring Boot:   4.0.8
Group:         com.example
Artifact:      demo
Name:          demo
Packaging:     Jar
Java:          25
```

- Spring Initializr currently lists Spring Boot 4.0.8 as a stable option and Java 25 as supported.
- Click Add Dependencies and select:

```text
Spring Web
```

- Then click:

```text
Generate
```

- You'll get something like: demo.zip

**.NET mental mapping**
- At this point think:

```text
Spring Initializr
       ↓
dotnet new webapi
```

- And: 


```text
Java                 .NET

java                  dotnet runtime
javac                 C# compiler
mvn                   dotnet/MSBuild + package tooling
pom.xml               .csproj
JDK                   .NET SDK
JVM                   CLR
```

