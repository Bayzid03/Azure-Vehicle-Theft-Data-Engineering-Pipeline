# 🚗 Azure Vehicle Theft Data Engineering Pipeline

> **Cloud-native data platform with hybrid connectivity for vehicle theft analytics using Azure services**

[![Azure](https://img.shields.io/badge/Azure-Cloud%20Platform-0078D4?style=flat-square&logo=microsoft-azure)](https://azure.microsoft.com/)
[![Databricks](https://img.shields.io/badge/Databricks-Lakehouse-FF3621?style=flat-square&logo=databricks)](https://databricks.com/)
[![Data Factory](https://img.shields.io/badge/ADF-ETL%20Orchestration-0078D4?style=flat-square)](https://azure.microsoft.com/en-us/products/data-factory/)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboards-F2C811?style=flat-square&logo=power-bi)](https://powerbi.microsoft.com/)

## 🎯 Overview

An **enterprise-grade data engineering solution** migrating on-premises vehicle theft data to Azure cloud, implementing **Medallion Architecture** for data quality progression, and delivering actionable insights through interactive Power BI dashboards.

### ✨ Key Features

- **🔄 Hybrid Integration** - Self-Hosted Integration Runtime for on-premises data ingestion
- **🏗️ Medallion Architecture** - Bronze (raw) → Silver (cleansed) → Gold (business-ready)
- **🔐 Enterprise Security** - Azure Key Vault for secrets management
- **⚡ Databricks Processing** - PySpark transformations at scale
- **💾 Data Lake Storage** - ADLS Gen2 for scalable, cost-effective storage
- **📊 Real-time Analytics** - Power BI with DirectQuery for live dashboards
- **☁️ Fully Managed** - Zero infrastructure maintenance with Azure PaaS services

## 🏗️ Architecture

```
┌──────────────────────────────────────────────────────────────┐
│               ON-PREMISES DATA SOURCE                        │
├──────────────────────────────────────────────────────────────┤
│  📂 Local File System                                        │
│  • Vehicle theft records (CSV/Delimited files)               │
│  • Historical crime data                                     │
│  • Geographic information                                    │
└──────────────────────────────────────────────────────────────┘
                            ↓
                🔗 Self-Hosted Integration Runtime
              (Secure hybrid connectivity agent)
                            ↓
┌──────────────────────────────────────────────────────────────┐
│                   INGESTION LAYER                            │
├──────────────────────────────────────────────────────────────┤
│  🏭 Azure Data Factory (ADF)                                 │
│  • Copy Data Activity - File System → ADLS Gen2             │
│  • SHIR for secure on-prem access                           │
│  • Scheduled pipeline execution                              │
│  • Monitoring & logging                                      │
└──────────────────────────────────────────────────────────────┘
                            ↓
┌──────────────────────────────────────────────────────────────┐
│               BRONZE LAYER (Raw Landing)                     │
├──────────────────────────────────────────────────────────────┤
│  💾 Azure Data Lake Storage Gen2                            │
│  • Container: bronze                                         │
│  • Raw, unmodified data from source                          │
│  • Hierarchical namespace enabled                            │
│  • Versioning & lifecycle management                         │
└──────────────────────────────────────────────────────────────┘
                            ↓
                  🔐 Azure Key Vault Integration
            (Secure credential & connection management)
                            ↓
┌──────────────────────────────────────────────────────────────┐
│               TRANSFORMATION LAYER                           │
├──────────────────────────────────────────────────────────────┤
│  ⚡ Azure Databricks (Apache Spark)                         │
│  • Data cleansing & validation                               │
│  • Schema standardization                                    │
│  • Business logic implementation                             │
│  • Secret Scope for Key Vault access                         │
│  • Optimized Delta Lake format                               │
└──────────────────────────────────────────────────────────────┘
                            ↓
              ┌─────────────┴─────────────┐
              ↓                           ↓
┌────────────────────────────┐ ┌──────────────────────────────┐
│   SILVER LAYER (Cleansed)  │ │   GOLD LAYER (Aggregated)    │
├────────────────────────────┤ ├──────────────────────────────┤
│  💾 ADLS Gen2 Container    │ │  💾 ADLS Gen2 Container      │
│  • Data quality validated  │ │  • Business KPIs & metrics   │
│  • Duplicates removed      │ │  • Aggregated by region/time │
│  • Type conversions        │ │  • Optimized for BI queries  │
│  • Null handling           │ │  • Dimensional modeling      │
└────────────────────────────┘ └──────────────────────────────┘
                                           ↓
┌──────────────────────────────────────────────────────────────┐
│               ANALYTICS & VISUALIZATION                      │
├──────────────────────────────────────────────────────────────┤
│  📊 Power BI                                                 │
│  • DirectQuery connection to ADLS Gen2                       │
│  • Interactive dashboards & reports                          │
│  • Theft trends & hotspot analysis                           │
│  • Geographic visualization                                  │
│  • Real-time metric updates                                  │
└──────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────┐
│               SECURITY & GOVERNANCE                          │
├──────────────────────────────────────────────────────────────┤
│  🔐 Azure Key Vault                                          │
│  • Storage account access keys                               │
│  • Service principal credentials                             │
│  • Connection strings                                        │
│  🛡️ Azure Active Directory                                  │
│  • Role-based access control (RBAC)                          │
│  • Managed identities for services                           │
└──────────────────────────────────────────────────────────────┘
```

## 🛠️ Technical Stack

### **Data Ingestion & Orchestration**
- **🏭 Azure Data Factory (ADF)** - ETL orchestration with visual designer
- **🔗 Self-Hosted Integration Runtime** - Secure on-premises connectivity
- **📂 File System Connector** - Ingest CSV/delimited files from local servers

### **Storage & Data Lake**
- **💾 Azure Data Lake Storage Gen2** - Hierarchical namespace for big data
- **🗂️ Medallion Architecture** - Bronze, Silver, Gold containers
- **⚡ Delta Lake Format** - ACID transactions in Databricks

### **Processing & Transformation**
- **⚡ Azure Databricks** - Unified analytics platform (Apache Spark)
- **🐍 PySpark** - Distributed data processing
- **🔐 Secret Scopes** - Secure Key Vault integration

### **Security & Governance**
- **🔑 Azure Key Vault** - Centralized secrets management
- **🛡️ Azure Active Directory** - Identity & access management
- **📋 RBAC** - Granular permission controls

### **Analytics & Reporting**
- **📊 Power BI** - Interactive dashboards with DirectQuery
- **📈 DAX Calculations** - Advanced metrics and KPIs
- **🗺️ Geographic Visualization** - Heat maps and regional analysis

## 🚀 Quick Start

### Prerequisites
- Azure subscription with appropriate permissions
- On-premises server with vehicle theft data
- Power BI Desktop (for dashboard development)

### Setup Instructions

```bash
# 1. Create Resource Group
az group create --name rg-vehicle-theft --location eastus

# 2. Create Storage Account
az storage account create \
  --namestvehicletheft \
  --resource-group rg-vehicle-theft \
  --location eastus \
  --sku Standard_LRS \
  --kind StorageV2 \
  --enable-hierarchical-namespace true

# 3. Create containers
az storage container create --name bronze --account-name stvarehicletheft
az storage container create --name silver --account-name stvarehicletheft
az storage container create --name gold --account-name stvarehicletheft
```

### Azure Data Factory Configuration

1. **Create Data Factory**
   ```bash
   az datafactory create \
     --resource-group rg-vehicle-theft \
     --factory-name adf-vehicle-theft
   ```

2. **Setup Self-Hosted Integration Runtime**
   - Navigate to ADF → Manage → Integration Runtimes
   - Create new → Azure, Self-hosted → Self-Hosted
   - Download and install runtime on on-premises server
   - Register with authentication key

3. **Create Linked Services**
   - **Source**: File System (SHIR, local path, credentials)
   - **Sink**: ADLS Gen2 (storage account, container)

4. **Build Copy Pipeline**
   - Add Copy Data activity
   - Configure source dataset (File System, Delimited Text)
   - Configure sink dataset (ADLS Gen2, Bronze container)
   - Set schedule trigger (daily, hourly, etc.)

### Azure Key Vault Setup

```bash
# Create Key Vault
az keyvault create \
  --name kv-vehicle-theft \
  --resource-group rg-vehicle-theft \
  --location eastus

# Add storage account key as secret
STORAGE_KEY=$(az storage account keys list \
  --account-name stvarehicletheft \
  --query '[0].value' -o tsv)

az keyvault secret set \
  --vault-name kv-vehicle-theft \
  --name storage-account-key \
  --value "$STORAGE_KEY"
```

### Databricks Configuration

1. **Create Workspace**
   ```bash
   az databricks workspace create \
     --resource-group rg-vehicle-theft \
     --name dbw-vehicle-theft \
     --location eastus \
     --sku premium
   ```

2. **Create Secret Scope**
   - Navigate to: `https://<databricks-instance>#secrets/createScope`
   - Scope Name: `vehicle-theft-scope`
   - DNS Name: `https://kv-vehicle-theft.vault.azure.net/`
   - Resource ID: (from Key Vault properties)

3. **Access Secrets in Notebooks**
   ```python
   storage_key = dbutils.secrets.get(scope="vehicle-theft-scope", 
                                      key="storage-account-key")
   
   spark.conf.set(
       "fs.azure.account.key.stvarehicletheft.dfs.core.windows.net",
       storage_key
   )
   ```

### Power BI Connection

1. **Get Data** → Azure → Azure Data Lake Storage Gen2
2. **Account URL**: `https://stvarehicletheft.dfs.core.windows.net`
3. **Container**: `gold`
4. **Connection Mode**: DirectQuery (for real-time updates)
5. **Authentication**: Azure AD or Access Key

## 📊 Data Transformations

### **Bronze → Silver (Cleansing)**
```python
# Read raw data
bronze_df = spark.read.csv("abfss://bronze@stvarehicletheft.dfs.core.windows.net/")

# Data quality checks
silver_df = (bronze_df
    .dropDuplicates()                           # Remove duplicates
    .dropna(subset=["vehicle_id", "theft_date"]) # Remove critical nulls
    .withColumn("theft_date", to_date("theft_date"))  # Type conversion
    .withColumn("location", upper(col("location")))   # Standardization
)

# Write to Silver
silver_df.write.format("delta").mode("overwrite").save(
    "abfss://silver@stvarehicletheft.dfs.core.windows.net/"
)
```

### **Silver → Gold (Aggregation)**
```python
# Read cleansed data
silver_df = spark.read.format("delta").load(
    "abfss://silver@stvarehicletheft.dfs.core.windows.net/"
)

# Business logic & aggregations
gold_df = (silver_df
    .groupBy("region", "month", "vehicle_type")
    .agg(
        count("vehicle_id").alias("total_thefts"),
        avg("recovery_rate").alias("avg_recovery_rate"),
        sum("value_stolen").alias("total_value")
    )
)

# Write to Gold
gold_df.write.format("delta").mode("overwrite").save(
    "abfss://gold@stvarehicletheft.dfs.core.windows.net/"
)
```

## 📁 Project Structure



## 🎯 Key Metrics & KPIs

### **Power BI Dashboard Features**
- **📊 Total Thefts by Region** - Geographic heat map
- **📈 Monthly Trend Analysis** - Time-series charts
- **🚗 Vehicle Type Breakdown** - Category distribution
- **💰 Total Value Stolen** - Financial impact metrics
- **🔄 Recovery Rate** - Success rate by region
- **⚠️ Hotspot Identification** - High-risk area alerts

## 🌟 Technical Highlights

### **Hybrid Cloud Integration**
- **Seamless on-prem to cloud** data flow with SHIR
- **Secure authentication** through Azure AD
- **Automatic failover** and retry logic in ADF

### **Data Quality & Governance**
- **Schema validation** in Silver layer
- **Duplicate detection** and removal
- **Null handling** strategies
- **Audit logging** throughout pipeline

### **Performance Optimization**
- **Delta Lake** for ACID transactions
- **Partitioning** by date and region
- **Caching** frequently accessed data
- **DirectQuery** optimization in Power BI

### **Security Best Practices**
- **No hardcoded credentials** - all in Key Vault
- **Managed identities** for service-to-service auth
- **RBAC** at storage container level
- **Network isolation** with private endpoints

## 🎯 Real-world Use Cases

- **🚔 Law Enforcement** - Crime pattern analysis and resource allocation
- **🏢 Insurance Companies** - Risk assessment and premium calculation
- **🏙️ City Planning** - Urban safety initiatives and infrastructure
- **📊 Government Analytics** - Policy effectiveness measurement
- **🚗 Automotive Industry** - Anti-theft technology development

## 🚀 Future Enhancements

- [ ] **🤖 Predictive Analytics** - ML models for theft risk prediction
- [ ] **📱 Real-time Streaming** - Event Hubs for live data ingestion
- [ ] **🗺️ Geospatial Analysis** - Advanced location intelligence
- [ ] **📧 Alert System** - Automated notifications for anomalies
- [ ] **🔗 External API Integration** - Weather, events, demographics
- [ ] **⚡ Incremental Processing** - Change Data Capture for efficiency

## 🤝 Contributing

Contributions welcome! Focus areas:
- **📊 Additional Visualizations** - New Power BI charts and KPIs
- **🔧 Pipeline Optimization** - Performance tuning and cost reduction
- **🛡️ Security Enhancements** - Advanced governance features
- **📈 ML Integration** - Predictive models with Azure ML

## 📄 License

MIT License - See [LICENSE](LICENSE) for details.

---

**Secure, scalable vehicle theft analytics powered by Azure** 🚗☁️
