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

## Step 3: Look at pom.xml
- Open:

```text
pom.xml
```

- You'll find something along these lines:

```xml
<project>
...
 
<groupId>com.example</groupId>
<artifactId>taskmanager</artifactId>
<version>0.0.1-SNAPSHOT</version>
 
<properties>
<java.version>21</java.version>
</properties>
 
<dependencies>
...
</dependencies>
 
</project>
```

- groupId

```xml
<groupId>com.example</groupId>
```

- This identifies the organization/group producing the artifact.
- You'll commonly see things like:

```tezt
org.springframework
org.apache.maven
com.fasterxml.jackson
```

- Don't think of groupId as a C# namespace, although they are often related.

-artifactId

```xml
<artifactId>taskmanager</artifactId>
```

-This identifies this particular project/artifact.
-Together:

```text
com.example:taskmanager
```

- is roughly Maven's identity for your artifact.
- You'll encounter this constantly in Java

## Step 4: Look at dependencies
- You'll see dependencies in the POM.
- For example, there will be Spring web functionality represented as a Maven dependency.
- Your mental model should be:
- **.NET**

```xml
<ItemGroup>
    <PackageReference Include="Something" Version="..." />
</ItemGroup>
```

- **Maven**

```xml
<dependencies>

    <dependency>
        <groupId>...</groupId>
        <artifactId>...</artifactId>
    </dependency>

</dependencies>
```

- You'll notice something interesting.
- There frequently isn't a:

```xml
<version>...</version>
```

- on every Spring dependency.
- Don't assume that means "latest version."
- Spring Boot provides dependency management so compatible versions of many dependencies can be managed centrally.