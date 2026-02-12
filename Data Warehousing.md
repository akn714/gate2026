
![[Pasted image 20260212194719.png]]

#### ETL (Extract, Transform, Load)
- Three-phase process where data is extracted, transformed and loaded into an output data container.
- Done by application software but can also be done manually.
#### Data warehouse
- Holds multiple subject areas
- Holds very detailed information
- Works to integrate all data sources
#### Data mart:
- Often holds only one subject area (eg. finance or sales)
- May hold more summarized data (although it may hold full detail)

#### Data Warehousing Architecture
- Top-down approach (data sources -> ETL -> data warehouse -> data marts -> data mining)
- Bottom-up approach (data sources -> ETL -> data marts -> data warehouse -> data mining)

---
#### Online Transaction Processing (OLTP)
- Happens on DB.
- Type of data processing that consists of executing a number of transactions occurring concurrently.
- Fast response time.
- Involves data modification.
- Require small storage space.

#### Online Analytical Processing (OLAP)
- Happens on Data Warehouse.
- Software for performing multidimensional analysis at high speeds on large volumes of data from a data warehouse, data mart, or some other unified, centralized data store.
- Does not involve data modification.
- Require larger storage space.

---

### Data Warehouse Design Schema
##### Two tables involved
- Dimension Table
	- holds descriptive information for all related fields that are included in the fact table's records.
	- Eg. Normal table to store data
- Fact Table
	- Eg. Store facts like sales data (which product was sold on which data and how many units)

##### Schemas
1. Star Schema
	- denormalized tables
	- all dimension tables are connected to only one fact table
2. Snowflake Schema 
	- normalized tables
	- all dimension tables are connected to only one fact table
3. Fact Constellation Schema (Galaxy Schema)
	- dimension tables can connect to more than one fact table

---

#### Data Transformation
1. Data Cleaning (remove null values, duplicate values)
2. Data Smoothing (making all data of same type)
3. Attribute Construction
4. Data Discretization (make data discontinues, histogram)
5. Data Generalization (replace values with general values)
6. Data Normalization
![[Pasted image 20260212223632.png]]

#### Sampling
The data-analysis practice of analyzing a subset of data in order to uncover meaningful information from a large dataset.

#### Data Compression
- compressing the data because it is too large in size.
1. Lossless
2. Lossy

#### Advanced SQL
```sql
select country, state, city, sum(Amount) as total_amount
from orders
gropu by rollup(country, state, city)

-- first gropu by city then state and then country at last
```

#### Window Function
![[Pasted image 20260212230942.png]]

#### Ranking Window function
![[Pasted image 20260212231033.png]]

