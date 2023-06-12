# Steps to Upgrade Delta tables to Unity Catalog

This article describes how to upgrade tables and views registered in your existing Hive metastore to Unity Catalog.
You can copy complete schemas (databases) and multiple external tables from your default Hive metastore to the Unity Catalog metastore using the Data Explorer upgrade wizard.

## Pre-requisites

- Unity Catalog should be enabled.
- A storage credential that contains the information about a service principal authorized to access the table’s location path.

![StorageCredentials](./images/storage_credentials_customer_SP.png)

- An external location that references the storage credential you just created and the path to the data on your cloud tenant.

![ExternalLocations](./images/external_location_customer.png)

- Catalog should be created. Steps to create catalog can be found [here](https://developer.elanco.com/dataops/5-unitycatalog/createcatalog).

![catalog](./images/ednacatalog_databricks.png)

## Steps

- Click Data Icon Data in the sidebar to open the Data Explorer.
- Create respective schemas in new catalog ( e.g., customer_raw, customer_stage)and grant required privileges to AZ group.

![edna_catalog schema](./images/ednacatalog_customer_schema.png)

- Select hive_metastore table that you want to upgrade.

![hivemetastoreschema](./images/hivemetastore_schemas.png)

- It will give an ***Upgrade*** option on the top right corner. Click on upgrade.

![upgrade_step1](./images/UnityCatalog_upg_step1.png)

- Once you click on Upgrade, it will ask to select the catalog, schema and the owner of the table.

![upgrade_step2](./images/unitycatalog_Upg_step2.png)

- Click on Next after selecting, it will navigate to the Upgrade step. Click on ***Run upgrade*** button.

![upgrade_step3](./images/UnityCatalog_Upg_step3.png)

- Finally upgrade is completed!

![upgrade_step4](./images/UnityCatalog_Upg_step4.png)

- After upgrading the tables, it can viewed under ***edna_catalog*** schemas.

![UnityCatalog_allschemas](./images/UC_upgraded_tables.png)
