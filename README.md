# # Employee Data Management with Solr

This project provides a set of functions to manage employee data in a Solr collection. The functions include creating collections, indexing data, searching for specific records, counting employees, deleting records by ID, and retrieving department facets.

## Prerequisites

- **Apache Solr**: Make sure you have Solr installed and running. You can download it from the official [Solr website](https://solr.apache.org/downloads.html).
- **Python**: Ensure you have Python installed on your machine. You can download it from the official [Python website](https://www.python.org/downloads/).
- **pysolr**: This Python library is used to interact with Solr. Install it using pip:
  ```bash
  pip install pysolr

#Function Definitions
#The following functions are implemented to manage employee data in Solr:

createCollection(p_collection_name): Creates a new collection in Solr with the specified name.

indexData(p_collection_name, p_exclude_column): Indexes employee data into the specified collection, excluding the specified column.

searchByColumn(p_collection_name, p_column_name, p_column_value): Searches for records in the specified collection where the specified column matches the provided value.

getEmpCount(p_collection_name): Retrieves the count of employees in the specified collection.

delEmpById(p_collection_name, p_employee_id): Deletes an employee record from the specified collection using the provided employee ID.

getDepFacet(p_collection_name): Retrieves the count of employees grouped by department from the specified collection.

#Usage
#Function Executions
# Define collection names
v_nameCollection = 'Hash_<Your Name>'
v_phoneCollection = 'Hash_<Your Phone last four digits>'

# Execute function calls in order
createCollection(v_nameCollection)
createCollection(v_phoneCollection)
getEmpCount(v_nameCollection)
indexData(v_nameCollection, 'Department')
indexData(v_phoneCollection, 'Gender')
delEmpById(v_nameCollection, 'E02003')
getEmpCount(v_nameCollection)
searchByColumn(v_nameCollection, 'Department', 'IT')
searchByColumn(v_nameCollection, 'Gender', 'Male')
searchByColumn(v_phoneCollection, 'Department', 'IT')
getDepFacet(v_nameCollection)
getDepFacet(v_phoneCollection)

#Running Solr with Docker
#To run Apache Solr using Docker, follow these steps:

Pull the Solr Docker Image:
  docker pull solr:9.7.0
Run Solr Container:  
  docker run -d -p 8983:8983 --name my_solr solr:9.7.0

Access Solr Admin UI: Open your browser and go to http://localhost:8983/solr/ to access the Solr Admin UI.  

