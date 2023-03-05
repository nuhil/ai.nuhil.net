# Apache Avro

[Apache Avro](https://avro.apache.org/docs/current/) is a data serialization format. We can store data as `.avro` files on disk. Avro files are typically used with Spark but Spark is completely independent of Avro. Avro is a row-based format that is suitable for evolving data schemas. One benefit of using Avro is that schema and metadata travels with the data. If you have an `.avro` file, you have the schema of the data as well. The [Apache Avro Specification](https://avro.apache.org/docs/current/spec.html) provides easy-to-read yet detailed information.
