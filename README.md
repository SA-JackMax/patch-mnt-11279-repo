
Alfresco Patch to allow Microsoft Office transformation for documents with accented characters in name
======================================================================================================

Described at issue [MNT-15359](https://issues.alfresco.com/jira/browse/MNT-15359)

**Description**

When a Microsoft Office document containing accented characters in the name is uploaded into Share, the transformation fails with the message:
conversion failed; com.sun.star.lang.IllegalArgumentException: Unsupported URL <file:///opt/alfresco/tomcat/temp/Alfresco/DEMISS%C3%95ES%20JUNHO.XLSX-OpenOfficeContentTransformer-OpenOfficeContentTransformer-1512413739507/DEMISS%C3%95ES%20JUNHO.XLSX>: "type detection failed" 

This patch changes the way the temporary file is writen in the server's disk, and **should be used only with version 5.1.g**, as this is a backport of code from already fixed more recent versions of Alfresco. 

The code is based on the proposed fix from https://issues.alfresco.com/jira/browse/MNT-15359, in combination with the current code from https://github.com/Alfresco/community-edition-old/blob/master/projects/repository/source/java/org/alfresco/repo/content/transform/OOoContentTransformerHelper.java#L354 

**License**
The plugin is licensed under the [LGPL v3.0](http://www.gnu.org/licenses/lgpl-3.0.html).

**State**
Current patch release is 1.0

**Compatibility**
The current version has been developed using Alfresco 5.1.g and Alfresco SDK 3.0.1

***No original Alfresco resources have been overwritten***

Downloading the ready-to-deploy-plugin
--------------------------------------
The binary distribution is made of one amp file to be deployed in Alfresco as a repo module at releases tab.

You can install them by using standard Alfresco deployment tools in alfresco.war


Building the artifacts
----------------------
You can build the artifacts from source code using maven
```$ mvn clean package```