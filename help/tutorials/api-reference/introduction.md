---
title: Introduction
description: Introduction to the API Reference Guide for AEM Guides
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
---
# Introduction {#id1761C0007W7}

Adobe Experience Manager Guides \(later referred as *AEM Guides*\) is an end-to-end, enterprise solution that enables Adobe Experience Manager \(AEM\) to have component content management solution \(CCMS\) capabilities for DITA-based content creation and delivery. Customers can access AEM Guides workflows programmatically using the AEM Guides APIs to integrate it with other enterprise applications. These APIs can also be used by Adobe partners to enhance the value proposition of AEM Guides by extending its functionality or by integrating it with other applications or services.

## AEM Guides APIs 

The AEM Guides APIs are available in two formats: HTTP and Java. These APIs expose key functions of AEM Guides to application developers. Using these functions, developers can create their own plug-ins to extend the out-of-the-box workflows. The APIs are available around managing outputs for DITA content, working with DITA maps, adding conditional attributes to folder-level profiles, and converting HTML and Words documents to DITA format.

## Installing the JARs on your local Apache Maven repository {#install-jar-local}

To be able to use the JAR files exposed by AEM Guides, you need to install them on your local Apache Maven repository. Perform the following steps to install the JARs on your location Maven repository:

1. Extract the contents of the AEM Guides package \(.zip\) file on your local system.

2. In the command prompt, navigate to the following folder in the extracted content path:

   ```
   \jcr_root\libs\fmdita\osgi-bundles\install
   ```

3. Run the following command to install the API bundle to your local Maven repository:

   ```
   mvn install:install-file -Dfile=api-X.x.jar -DgroupId=com.adobe.fmdita -DartifactId=api -Dversion=X.x -Dpackaging=jar**
   ```

    >[!NOTE]
    >
    > In the above command, X.x should be replaced with the actual version number in the Dfile and Dversion parameters.

4.  \(*Optional*\) Install dependency in your local Maven project's repository. You can achieve this by creating a folder in your Maven project and then running the `mvn install` command given in the previous step with the following additional parameter:

    ```
    -DlocalRepositoryPath=<path_to_project_repository>
    ```

    Next, to expose the project's local repository folder to the Maven build process, add a `repository` element in the parent pom.xml file as shown below:

    ```XML
    <repositories>
       <repository>
          <id>project-repository</id>
          <url>file://${project.basedir}/repository</url>
       </repository>
    </repositories>
    ```


This process installs the API JARs in the local Maven repository.

## Using the service API JAR in a Maven project 

After installing the API JARs in your local Maven repository, perform the following steps to use the JAR in your projects:

1.  Add the JAR to your code base and commit it to the code base repository under a folder, such as "dependencies". Note that the folder name depends on your code base hierarchy.

2.  Configure the project pom.xml files as follows:

    Parent project's pom.xml file:

    >[!IMPORTANT]
    >
    > In the following code snippet, X.x should be replaced with the actual version number and the API JAR's file name. This information will be same as given in the Step 3 of the [installation process](#install-jar-local).

    ```XML
    <plugin>
    
        <groupId>org.apache.maven.plugins</groupId>
                         
       <artifactId>maven-install-plugin</artifactId>
    
        <version>2.5.2</version>
    
        <configuration>
    
                <groupId>com.adobe.fmdita</groupId>
    
                <artifactId>api</artifactId>
    
                <version>X.x</version>
    
                <file>${basedir}/dependencies/fmdita/api-X.x.jar</file>
    
                <packaging>jar</packaging>
    
                <generatePom>true</generatePom>
    
        </configuration>
    
        <executions>
    
            <execution>
    
                <id>inst_fmdita</id>
    
                    <goals>
    
                        <goal>install-file</goal>
    
                    </goals>
    
                    <phase>clean</phase>
    
            </execution>
    
        </executions>
    </plugin>
    ```

    Child module's pom.xml file:

    ```XML
    <plugin>
       <groupId>org.apache.maven.plugins</groupId>
    
       <artifactId>maven-install-plugin</artifactId>
    
       <configuration>
    
          <groupId>com.adobe.fmdita</groupId>
    
          <artifactId>api</artifactId>
    
          <version>3.6</version>
    
          <file>${basedir}/../dependencies/fmdita/api-3.6.jar</file>
    
          <packaging>jar</packaging>
    
          <generatePom>true</generatePom>
    
       </configuration>
    
       <executions>
    
          <execution>
    
             <id>inst_fmdita</id>
    
             <goals>
    
                <goal>install-file</goal>
    
             </goals>
    
             <phase>clean</phase>
    
          </execution>
    
       </executions>
    
    </plugin>
    ```


## Configure and use the service API JAR from public Maven repository 

Perform the following steps to configure and use the service API JARs from the public Maven repository in your projects:

1.  To use the service API JAR in a project, configure AEM Guides public Maven repository in your pom.xml file.
2.  Configure the public Maven repository in Maven's settings.xml file as follows:

    ```XML
    <repository>
       <id>fmdita-public</id>
       <name>fmdita-public</name>
       <url>https://repo.aem-guides.com/repository/fmdita-public</url>
    </repository>
    ```

3.  Once the repository is setup, add the service API JAR as a project dependency in the project's pom.xml file.

    >[!NOTE]
    >
    > Use the same version of the API JAR as the AEM Guides package which you have installed on the server.

4.  Configure the Maven dependency as shown below:

    ```XML
    <dependency>
       <groupId>com.adobe.fmdita</groupId>
       <artifactId>api</artifactId>
       <version>4.0</version>
    </dependency>
    ```


Once service API JAR is added as a project dependency in the project's pom.xml file, you can build and use AEM Guides Java APIs in your project.

## Using API JAR from Maven Central repository for AEM Guides as a Cloud Service 

For AEM Guides as a Cloud Service the API JAR has been deployed to Maven Central. You can use the API JAR without any setup.

>[!NOTE] 
>
> The naming convention of the API jar has been updated as per the cloud add-ons naming convention.

To use the API JAR, you need to add the dependency to your project's pom.xml as shown below:

```XML
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-guides-sdk-api</artifactId>
   <version>2022.5</version>
</dependency>
```

>[!NOTE] 
>
> Since the packages inside the API JAR are still the same, no code change is required to use this API JAR in the existing cloud projects.

## Additional resources 

Following is a list of other helpful resources of AEM Guides, which are available on the [Learn & Support](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html) page:

-   User Guide
-   Installation and Configuration Guide
-   Quick Start Guide
-   [Help Archival Page](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) \(access older release documentation\)
