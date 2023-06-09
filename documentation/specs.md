# Tax and Soil Data Integration for High Land Value Identification

## Diagram:

- [Soil-real-value-graph](soil-real-value-graph.md):

```mermaid
graph TD
    A(Data Acquisition) --> B(Data Preparation)
    B --> C(Data Integration)
    C --> D(Data Analysis)
    D --> E(Data Output)
    E --> F(Testing)
    F --> G(Documentation)
    D --> H(Maintenance)
    H --> I(Deployment and Monitoring)

    style A fill:#a6cee3, stroke:#9999,stroke-width:4px;
    style B fill:#a6cee3,stroke:#9999,stroke-width:4px;
    style C fill:#a6cee3,stroke:#9999,stroke-width:4px;
    style D fill:#a6cee3,stroke:#9999,stroke-width:4px;
    style E fill:#a6cee3,stroke:#a999,stroke-width:4px;
    style F fill:#a6cee3,stroke:#9999,stroke-width:4px;
    style G fill:#a6cee3,stroke:#9999,stroke-width:4px;
    style H fill:#a6cee3,stroke:#9999,stroke-width:4px;
    style I fill:#a6cee3,stroke:#9999,stroke-width:4px;
```

## Objective

To create a test-driven development (TTD) script that identifies areas with high land value by combining soil data with tax information. The script will perform ETL operations, various SQL techniques, and calculations for a robust analysis.

## Requirements

- Soil Data: A dataset containing information about soil quality, location, and other relevant attributes.
- Tax Data: A dataset containing tax information about land value, property tax rates, and location.

## Assumptions

1. Both datasets have a common location identifier, such as a parcel ID, to join the datasets.
2. The tax dataset is available in a structured format (CSV, Excel, JSON, or XML).

## Steps

### 1. Data Acquisition

a. Obtain soil data.

- 🔰 [04-16-2023] already in a structured format [soilsite_world `CSV`](../assets/datasets/soilsite_full.csv)

b. Obtain tax data (from a reliable source, e.g., local government or paid service).

- 🔰[04-16-2023] [Link to data potential open data sources](open-property-data-resources.md)

> - **Notes**:
> - For now, all but PropMix appears as a second option. PropMix is a new API that I haven't had a chance to test yet. I'll update this section once I've had a chance to test some of these APIs.
> - **Propose** to check on **insurance data**, and other data sources that might be useful for this project to find real value of land or property.

### 2. Data Preparation

a. Load both datasets into a staging area (e.g., a relational database or a data warehouse).
b. Clean and standardize the datasets (e.g., address missing values, standardize date formats, and remove duplicates).
c. Create indexes on location identifiers for faster querying and joining.

### 3. Data Integration

a. Join the soil and tax datasets on the common location identifier (e.g., parcel ID).
b. Select relevant attributes from both datasets (e.g., soil quality, land value, property tax rates, and location).

### 4. Data Analysis

a. Calculate a "Land Value Score" using a combination of land value, property tax rates, and soil quality. This can be a weighted average or a more complex formula based on domain knowledge.
b. Rank the joined dataset based on the "Land Value Score."
c. Identify a threshold for "high land value" areas (e.g., top 10%, or a specific Land Value Score).

### 5. Data Output

a. Generate a report (CSV, Excel, or JSON) with the identified high land value areas, including their Land Value Score and relevant attributes.
b. Optionally, visualize the results on a map using geospatial tools or libraries (e.g., QGIS, ArcGIS, or a Python library like Geopandas).

### 6. Testing

a. Develop test cases to ensure the ETL process is working correctly (e.g., data loading, cleaning, and joining).
b. Develop test cases to validate the Land Value Score calculations.
c. Develop test cases to verify the threshold for high land value areas.
d. Develop test cases to ensure the output report is generated correctly.

### 7. Documentation

a. Document the entire process, including data sources, data preparation steps, analysis methods, and testing procedures.
b. Include comments in the code for better understanding and maintainability.

### 8. Maintenance

a. Schedule regular updates to the datasets.
b. Monitor the system for any data quality issues or changes in the underlying data structures. Use dates to track any updates when feasible.. For example,

> "[04-16-2023] Updated Open Soil Datasets:..."

c. Update the analysis and scoring methods as needed, based on new insights or changing market conditions.

### 9. Deployment

### 10. Monitoring

### 11. Maintenance

## Acknowledgements

---

# Actual rough steps

1. Get data, check table , inspect header titles or features to imagine what insight posibilities.
1. Device theory of how to use data to get insight in a valueable way.
1. Proppose a hythosis to test. I.e will high valued land have a higher soil quality?
1. setup file structure, readme, gitignore, requirements.txt, repo on github, description of project, license, etc.
1. Check excitance of data.
