---
title: Configure a data source connector
description: Learn how to configure a data source connector
exl-id: b7d09319-28d8-4f70-a641-03e8659442de
---
# Configure a data source connector 

AEM Guides provides out-of-the-box connectors for JIRA and SQL (MySQL, PostgreSQL, SQL Server, SQLite) databases. You can also add other connectors by extending the default interfaces. The following configuration helps you to easily add the various data sources. Once added, you can view the data sources in the Web Editor. 

Perform the following steps to configure a data source connector and then use it from the Web Editor:

## Configure a connector

You can configure an out-of-the-box connector by uploading a JSON file. You can use the following sample setup files to set up connectors for Jira and SQL (MySQL, PostgreSQL, SQL Server, SQLite) databases.
  
A sample setup file for Jira's basic authentication with username and password:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
	"configName": "Jira",
	"templateFolders": ["/content/dam/dita-templates/konnect/jira"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
		"configData": {
			"username": "jirausername",
			"password": "jirapassword",
			"url": "https://jira.corp.adobe.com/rest/api/latest/search"
		}
	}
}
```

For example, save as `jira.json`.

A sample setup file for Jira's basic authentication with token:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
	"configName": "Jira",
	"templateFolders": ["/content/dam/dita-templates/konnect/jira"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
		"configData": {
			"token": "jiraauthtoken",
			"url": "https://jira.corp.adobe.com/rest/api/latest/search"
		}
	}
}
```

For example, save as `jira.json`.

A sample setup file for Jira's basic authentication with the token having "Basic" keyword present in it: 

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
	"configName": "Jira",
	"templateFolders": ["/content/dam/dita-templates/konnect/jira"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
		"configData": {
			"token": "Basic jiraauthtoken",
			"url": "https://jira.corp.adobe.com/rest/api/latest/search"
		}
	}
}
```

For example, save as `jira.json`.

A sample setup file for MySql's basic authentication:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MySqlConnector",
	"configName": "MySQL",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "com.mysql.jdbc.Driver",
			"connectionString": "jdbc:mysql://host.corp.adobe.com:3306/plm"
		}
	}
}
```

For example, save as `mysql.json`.

A sample setup file for PostgreSQL's basic authentication:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.PostgreSqlConnector",
	"configName": "PostgreSQL",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "org.postgresql.Driver",
			"connectionString": "jdbc:postgresql://host:port/database"
		}
	}
}
```

For example, save as `postgres.json`.

A sample setup file for MS SQL Server's basic authentication:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MsSqlServerConnector",
	"configName": "MSSQLServer",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "com.microsoft.sqlserver.jdbc.SQLServerDriver",
			"connectionString": "jdbc:sqlserver://10.10.10.10\\SQLEXPRESS01:1433;database=TutorialDB;encrypt=false;trustServerCertificate=true"
		}
	}
}
```

For example, save as `mssqlserver.json`.

A sample setup file for SQLite's basic authentication:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.SqliteConnector",
	"configName": "SQLiteServer",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "org.sqlite.JDBC",
			"connectionString": "jdbc:sqlite:sample.db"
		}
	}
}
```

For example, save as `sqqlite.json`.

### Customize a connector configuration

AEM Guides allows you to customize some values in the configuration file to meet the user’s needs.

|Property Name| Description|
|---|---|
|configName| The user can specify a configuration name to help identify the connector|
|templateFolders| List of Folders from where templates will be fetched|

Other fields are customized based on the config class selected to run the Connector.

## Upload the file to a location in AEM

Upload the file to some location in AEM Assets.

For example,  `/content/dam/jira.json`

## Create Configuration using REST API

You can register the configuration using REST API. For more details, view the *REST API to register a data source connector* section in the API Reference for Adobe Experience Manager Guides.

Once you have configured the data source, the connector is listed under the Data Sources panel in the Web Editor. You can then connect to the data source and insert a content snippet into your topics. For more details, view [Insert a content snippet from your data source](../user-guide/web-editor-content-snippet.md).
