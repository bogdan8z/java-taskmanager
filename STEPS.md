# Do a simple project (compare .net to java)
## Step 1: Create project in git

## Step 2: Create your first Spring Boot API

- Use Spring Initializr: Run:

```text
curl https://start.spring.io/starter.zip \
  -d type=maven-project \
  -d language=java \
  -d javaVersion=21 \
  -d groupId=com.example \
  -d artifactId=taskmanager \
  -d name=taskmanager \
  -d packageName=com.example.taskmanager \
  -d dependencies=web,data-jpa,validation,postgresql \
  -o taskmanager.zip
```

- you'll get taskmanager.zip

**.NET mental mapping**
- At this point think:

```text
Spring Initializr
       ↓
dotnet new webapi
```

- And: 

```text
Java                            .NET

java                            dotnet runtime
javac                           C# compiler
mvn                             dotnet/MSBuild + package tooling
pom.xml                         .csproj
JDK                             .NET SDK
JVM                             CLR
TaskmanagerApplication.java     Program.cs
application.properties          appsettings.json
target/                         bin/ + obj/
mvn / ./mvnw                    dotnet
Maven repositories              NuGet
```
- Extract

```text
unzip taskmanager.zip
rm taskmanager.zip
```