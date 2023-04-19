**What is MongoDB?**
- MongoDB is a general purpose document database used to build highly available and scalable internet applications.
- MongoDB stores data in flexible, JSON-like documents, meaning fields can vary from document to document and data structure can be changed over time.

**What are NoSQL databases? How do they differ from SQL?**
- MongoDB is categorized as NO SQL (Not Only SQL) database, as the storage and output of data is not in tables.
- Whereas SQL databases are stored and categorised in tables and columns.
- Each record in a MongoDB database is a document described in BSON, a binary representation of the data.
- Applications can then retrieve this information in a JSON format.

**Why is MongoDB popular? What is it’s history?**
- Founded in 2007, MongoDB has a worldwide following in the developer community. 
- It was built in a scale out architecture, where it allows many small machines to work together
- Adapted to handle huge amounts of data and is very fast.
- This format directly maps to native objects in most modern programming languages, making it a natural choice for developers, as they don’t need to think about normalizing data.

![image](https://user-images.githubusercontent.com/129324316/233049386-9b8686e4-9aa7-4a89-8358-92895eec084e.png)


**What is seeding in MongoDB? Why do Mongo databases need to be seeded?**
- Seeding your MongoDB database can help you to get some data within your Mongo collection
- Enables you to test out your queries without being restricted. 
- Seeding in its simplest way is more like inserting some dummy data initially into the database so that you can play around with it.

**What port does MongoDB use?**

- MongoDB uses TCP ports, its default ports include:
  - Port 27017: The default port for mongod and mongos instances. You can change this port with port or --port.
  - Port 27018: The default port for mongod when running with --shardsvr command-line option or the shardsvr value for the clusterRole setting in a configuration file.
  - Port 27019: The default port for mongod when running with --configsvr command-line option or the configsvr value for the clusterRole setting in a configuration file.
  - Port 27020: The default port from which mongocryptd listens for messages. mongocryptd is installed with MongoDB Enterprise Server (version 4.2 and later) and supports automatic encryption operations.
- These ports all have different uses

**How do you connect to a Mongo database?**
