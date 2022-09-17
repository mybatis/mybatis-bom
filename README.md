MYBATIS Bom
===========
[![build](https://github.com/mybatis/mybatis-bom/workflows/Java%20CI/badge.svg)](https://github.com/mybatis/mybatis-bom/actions?query=workflow%3A%22Java+CI%22)
[![Maven central](https://maven-badges.herokuapp.com/maven-central/org.mybatis/mybatis-bom/badge.svg)](https://maven-badges.herokuapp.com/maven-central/org.mybatis/mybatis-bom)
[![Sonatype Nexus (Snapshots)](https://img.shields.io/nexus/s/https/oss.sonatype.org/org.mybatis/mybatis-bom.svg)](https://oss.sonatype.org/content/repositories/snapshots/org/mybatis/mybatis-bom/)
[![License](https://img.shields.io/:license-apache-brightgreen.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)

![mybatis-bom](https://mybatis.org/images/mybatis-logo.png)

MyBatis-Bom is the MyBatis Bill of Materials that houses all the mybatis modules that are compatible for ease of use.

# Usage

In your pom, to use the bill of materials, simply add dependency management as follows.

```
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>org.mybatis</groupId>
            <artifactId>mybatis-bom</artifactId>
            <version>3.5.10-SNAPSHOT</version>
            <scope>import</scope>
            <type>pom</type>
        </dependency>
    </dependencies>
</dependencyManagement>
```

Then in dependencies section simply add the module you want to use without defining the version.  Any resolution needs for that product will resolve out as expected.

```
<dependencies>
    <dependency>
        <groupId>org.mybatis.spring.boot</groupId>
        <artifactId>mybatis-spring-boot-starter</artifactId>
    </dependency>
</dependencies>
```

# Corporate Procurements

Some corporations have procurement proceedures of external dependencies that can make it time consuming to load without a ```bom```.  When using such tool, simply import the bom pom file which will auto load the other modules thus simplifying the process.

# Resolution Issues

Occassionally, resolution in maven may not resolve out as expected even with a bom. This has to do with many products usage of same structure.  This can be a consideration when using spring boot where it could potentially suggest a specific mybatis version as an example.  To overcome such a situation, simply add the bom before the one that is not resolving properly in dependency management to force maven to use the expected order.

# License

Mybatis is [Apache Licensed](LICENSE)
