# Apache Avro

[Apache Avro](https://avro.apache.org/docs/current/) is a data serialization format. We can store data as `.avro` files on disk. Avro files are typically used with Spark but Spark is completely independent of Avro. Avro is a row-based format that is suitable for evolving data schemas. <mark style="background-color:green;">One benefit of using Avro is that schema and metadata travels with the data. If you have an</mark> <mark style="background-color:green;"></mark><mark style="background-color:green;">`.avro`</mark> <mark style="background-color:green;"></mark><mark style="background-color:green;">file, you have the schema of the data as well.</mark> The [Apache Avro Specification](https://avro.apache.org/docs/current/spec.html) provides easy-to-read yet detailed information.

```python
# Python 3 with `avro-python3` package available
import copy
import json
import avro
from avro.datafile import DataFileWriter, DataFileReader
from avro.io import DatumWriter, DatumReader

# Note that we combined namespace and name to get "full name"
schema = {
    'name': 'avro.example.User',
    'type': 'record',
    'fields': [
        {'name': 'name', 'type': 'string'},
        {'name': 'age', 'type': 'int'}
    ]
}

# Parse the schema so we can use it to write the data
schema_parsed = avro.schema.Parse(json.dumps(schema))

# Write data to an avro file
with open('users.avro', 'wb') as f:
    writer = DataFileWriter(f, DatumWriter(), schema_parsed)
    writer.append({'name': 'Pierre-Simon Laplace', 'age': 77})
    writer.append({'name': 'John von Neumann', 'age': 53})
    writer.close()

# Read data from an avro file
with open('users.avro', 'rb') as f:
    reader = DataFileReader(f, DatumReader())
    metadata = copy.deepcopy(reader.meta)
    schema_from_file = json.loads(metadata['avro.schema'])
    users = [user for user in reader]
    reader.close()

print(f'Schema that we specified:\n {schema}')
print(f'Schema that we parsed:\n {schema_parsed}')
print(f'Schema from users.avro file:\n {schema_from_file}')
print(f'Users:\n {users}')

# Schema that we specified:
#  {'name': 'avro.example.User', 'type': 'record',
#   'fields': [{'name': 'name', 'type': 'string'}, {'name': 'age', 'type': 'int'}]}
# Schema that we parsed:
#  {"type": "record", "name": "User", "namespace": "avro.example",
#   "fields": [{"type": "string", "name": "name"}, {"type": "int", "name": "age"}]}
# Schema from users.avro file:
#  {'type': 'record', 'name': 'User', 'namespace': 'avro.example',
#   'fields': [{'type': 'string', 'name': 'name'}, {'type': 'int', 'name': 'age'}]}
# Users:
#  [{'name': 'Pierre-Simon Laplace', 'age': 77}, {'name': 'John von Neumann', 'age': 53}]
```

### Third-party Avro Packages <a href="#third-party-avro-packages" id="third-party-avro-packages"></a>

While `avro-python3` is the official Avro package, it appears to be [very slow](https://medium.com/@abrarsheikh/benchmarking-avro-and-fastavro-using-pytest-benchmark-tox-and-matplotlib-bd7a83964453). This is because it is written in pure python. In comparison, [`fastavro`](https://github.com/fastavro/fastavro)uses C extensions (with regular CPython) making it much faster. Another benefit of using `fastavro` is that you can install it the same way in both Python 2 and Python 3. `fastavro` API is also the same[2](https://www.perfectlyrandom.org/2019/11/29/handling-avro-files-in-python/#fn:2) for both Python 2 and 3.



{% embed url="https://www.perfectlyrandom.org/2019/11/29/handling-avro-files-in-python/" %}
