# Metalib Spring POM

A comprehensive parent POM for Java Spring Boot applications that provides centralized dependency management,
plugin configurations, and best practices for enterprise-grade development.

The parent POM significantly reduces project setup time and ensures consistent build practices
across all Spring Boot applications in your organization.

## Overview

The `metalib-spring-pom` is a Maven parent POM designed to streamline Spring Boot application development by providing:
- Centralized version management for dependencies and plugins
- Pre-configured build plugins with sensible defaults
- Support for modern Java development tools and frameworks
- Cloud-native development support (GCP, AWS)
- Database migration and testing utilities

## Key Features

### 🏗️ **Modern Java Stack**
- **Java 21** support with optimized compiler settings
- **Spring Boot 3.4.5** and **Spring Framework 6.2.6**
- **Lombok 1.18.38** and **MapStruct 1.6.3** for code generation
- **JUnit 5.12.1** for modern testing practices

### 📦 **Comprehensive Dependency Management**
- **Cloud Providers**: Google Cloud Platform and AWS SDK integration
- **Database**: Liquibase for database migrations with multi-database support
- **Testing**: JUnit 5, Cucumber, ArchUnit, and JavaFaker
- **JSON Processing**: Jackson 2.19.0 and JSON Path utilities
- **Utilities**: Guava, SLF4J, Logback, and validation APIs

### 🔧 **Plugin Configuration**
- **Build Tools**: Maven compiler, surefire, failsafe plugins
- **Code Quality**: Checkstyle, PMD, JaCoCo for code coverage
- **Documentation**: Javadoc and site generation
- **Deployment**: Docker integration, release management
- **Development**: Version management, source attachment

## Benefits of Using as Parent Project

### 1. **Centralized Version Management**
```xml
<parent>
    <groupId>org.metalib.maven.pom</groupId>
    <artifactId>metalib-spring-pom</artifactId>
    <version>0.0.71-SNAPSHOT</version>
</parent>
```

All dependency versions are managed centrally, ensuring consistency across projects and eliminating version conflicts.

### 2. **Shared Dependencies**
The parent POM provides automatic inclusion of essential dependencies:
- **Lombok**: Reduces boilerplate code with annotations
- **MapStruct**: Type-safe bean mapping
- **Spring Boot**: Complete framework stack through BOM imports

### 3. **Pre-configured Plugins**
- **Maven Compiler Plugin**: Configured with Java 21 and annotation processors
- **Surefire/Failsafe**: Ready for unit and integration testing
- **Enforcer Plugin**: Ensures Maven version compliance
- **Release Plugin**: Streamlined release process with semantic versioning

### 5. **Cloud-Native Ready**
- Google Cloud Platform libraries BOM
- AWS SDK BOM
- Docker Maven plugin integration
- Secret management utilities

## Maven Properties Management

The parent POM provides extensive property management for versions:

### **Dependency Version Commands**
```textmate
# Check for dependency updates
mvn versions:display-dependency-updates

# Check for plugin updates  
mvn versions:display-plugin-updates

# Check for property updates
mvn versions:display-property-updates
```

### **Key Properties**
- `lombok.version`: 1.18.38
- `spring-boot.version`: 3.4.5
- `jackson.version`: 2.19.0
- `junit.version`: 5.12.1
- `liquibase.version`: 4.31.1

## Usage Example

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0">
    <modelVersion>4.0.0</modelVersion>
    
    <parent>
        <groupId>org.metalib.maven.pom</groupId>
        <artifactId>metalib-spring-pom</artifactId>
        <version>0.0.71</version>
    </parent>
    
    <groupId>com.example</groupId>
    <artifactId>my-spring-app</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    
    <dependencies>
        <!-- Spring Boot Starter -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        
        <!-- Testing -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>
    </dependencies>
</project>
```

## Target Audience

This parent POM is ideal for:
- Enterprise Spring Boot applications
- Microservices architectures
- Cloud-native applications (GCP)
- Teams requiring standardized build processes
- Projects needing comprehensive testing and quality tools

## Projects Using This Parent POM

The following projects demonstrate real-world usage of `metalib-spring-pom`:
- [org-metalib/api-wiser](https://github.com/org-metalib/api-wiser)
