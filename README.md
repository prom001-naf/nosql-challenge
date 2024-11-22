# NoSQL Challenge: UK Food Standards Analysis

## Instructions

The **UK Food Standards Agency** evaluates various establishments across the United Kingdom and assigns them food hygiene ratings. You have been contracted by the editors of the food magazine **Eat Safe, Love** to evaluate some of the ratings data to help their journalists and food critics decide where to focus future articles.

## Part 1: Database and Jupyter Notebook Setup

### Prerequisites
- **MongoDB**: Ensure MongoDB is installed and running on your system.
- **Python Libraries**: Install the required Python libraries:
   ```bash
   pip install pymongo pandas notebook
   ```
### Dataset
Download the `establishments.json` file provided.

---

### Steps

#### 1. Import Data into MongoDB
To import the data into MongoDB:

1. Open your terminal.
2. Use the following command to load the data:
   ```bash
   mongoimport --db uk_food --collection establishments --file establishments.json --jsonArray
   ```
### 2. Import Libraries in Jupyter Notebook

Within your notebook, import the following libraries to enable MongoDB interactions and formatted output:

```python
from pymongo import MongoClient
from pprint import pprint
```
### 3. Create a MongoDB Client

Create an instance of the MongoDB client to connect to the database:

```python
# Create an instance of MongoClient
mongo = MongoClient(port=27017)
```
### 4. Verify the Database and Data Import

#### List the Databases
Confirm that the `uk_food` database was created:

```python
print("Databases:")
print(mongo.list_database_names())
# Access the database
db = mongo['uk_food']

# List the collections
print("Collections in 'uk_food':")
print(db.list_collection_names())
# Access the collection
establishments = db['establishments']

# Find and print one document
document = establishments.find_one()
pprint(document)
---

### Rendered Markdown Output:
#### List the Databases
Confirm that the `uk_food` database was created:

```python
print("Databases:")
print(mongo.list_database_names())
```

### Deliverables

- A functioning MongoDB database (`uk_food`) with data imported.
- A Jupyter Notebook with:
  - Confirmation of the database (`uk_food`) and collection (`establishments`).
  - Display of a sample document using `find_one` and `pprint`.
