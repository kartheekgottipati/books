# Working with databases

In this chapter, we will explore working with databases in Python. We will discuss various types of databases, such as relational, NoSQL, and in-memory databases, and learn how to interact with them using Python libraries and Object-Relational Mapping (ORM) tools.

## Introduction to Databases

Databases are essential for storing, managing, and retrieving structured data in web applications. There are several types of databases, including:

- Relational Databases: These databases use tables to store data, and the relationships between the tables are defined using primary and foreign keys. Examples include MySQL, PostgreSQL, and SQLite.

- NoSQL Databases: These databases do not use tables and relationships, instead opting for other data models like document, key-value, column-family, or graph. Examples include MongoDB, Redis, Cassandra, and Neo4j.

- In-Memory Databases: These databases store data in memory, providing fast access and low latency, but may lose data when the system is shut down. Examples include Redis and Memcached.

## SQLite

SQLite is a lightweight, serverless, self-contained SQL database engine. It is widely used in embedded systems and mobile applications due to its low overhead and simplicity. Python includes built-in support for SQLite with the sqlite3 module.

Creating and Querying an SQLite Database:

```python
import sqlite3

# Connect to a database (or create one)
connection = sqlite3.connect('example.db')

# Create a cursor object
cursor = connection.cursor()

# Create a table
cursor.execute('CREATE TABLE IF NOT EXISTS users (id INTEGER PRIMARY KEY, name TEXT, age INTEGER)')

# Insert data
cursor.execute("INSERT INTO users (name, age) VALUES ('John Doe', 30)")
cursor.execute("INSERT INTO users (name, age) VALUES ('Jane Doe', 28)")

# Commit the changes
connection.commit()

# Query data
cursor.execute('SELECT * FROM users')
rows = cursor.fetchall()
for row in rows:
    print(row)

# Close the connection
connection.close()
```

## SQLAlchemy

SQLAlchemy is a Python SQL toolkit and Object-Relational Mapper (ORM) that provides a full suite of well-known enterprise-level persistence patterns, designed for efficient and high-performing database access, adapted into a simple and Pythonic domain language. It provides a set of high-level API to communicate with relational databases and a powerful, lower-level SQL expression language.

### Installation

```bash
$ pip install sqlalchemy
```

### Creating and Querying a SQLAlchemy Database

```python
from sqlalchemy import create_engine, Column, Integer, String
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.orm import sessionmaker

# Create an engine
engine = create_engine('sqlite:///example.db', echo=True)

# Create a base class
Base = declarative_base()

# Create a session
Session = sessionmaker(bind=engine)
session = Session()

# Define a user model
class User(Base):
    __tablename__ = 'users'

    id = Column(Integer, primary_key=True)
    name = Column(String)
    age = Column(Integer)

    def __repr__(self):
        return f'User(id={self.id}, name={self.name}, age={self.age})'

# Create the table
Base.metadata.create_all(engine)

# Create a user object
user = User(name='John Doe', age=30)

# Add the user to the session
session.add(user)

# Commit the changes
session.commit()

# Query data
users = session.query(User).all()
for user in users:
    print(user)

# Close the session
session.close()
```

## MongoDB with Python

MongoDB is a document-oriented NoSQL database that stores data in JSON-like documents. It is a cross-platform, open-source database that provides high performance, high availability, and automatic scaling.

### Installation

```bash
$ pip install pymongo
```

### Creating and Querying a MongoDB Database

```python
from pymongo import MongoClient

# Connect to a database
client = MongoClient('localhost', 27017)
db = client['example']

# Create a collection
collection = db['users']

# Insert data
collection.insert_one({'name': 'John Doe', 'age': 30})
collection.insert_one({'name': 'Jane Doe', 'age': 28})

# Query data
users = collection.find()
for user in users:
    print(user)

# Close the connection
client.close()
```

## Redis with Python

Redis is an in-memory data structure store, used as a database, cache, and message broker. It supports data structures such as strings, hashes, lists, sets, sorted sets with range queries, bitmaps, hyperloglogs, geospatial indexes with radius queries, and streams.

### Installation

```bash
$ pip install redis
```

### Creating and Querying a Redis Database

```python
import redis

# Connect to a database
r = redis.Redis(host='localhost', port=6379, db=0)

# Insert data
r.set('name', 'John Doe')
r.set('age', 30)

# Query data
print(r.get('name'))
print(r.get('age'))

# Close the connection
r.close()
```

## Conclusion

In this chapter, we learned about various types of databases, such as relational, NoSQL, and in-memory databases. We also learned how to interact with them using Python libraries and Object-Relational Mapping (ORM) tools.
