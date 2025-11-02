**Graph NoSQL Databases Overview:**

- **Definition:** Graph [[NoSQL]] databases are a category of NoSQL databases that store information in entities (nodes) and relationships (edges).
- **Architecture:** They are distinct from other NoSQL types due to their unique architecture, which is particularly effective for data that resembles a graph-like structure.
- **Performance:** Graph databases excel in traversing relationships quickly and efficiently. However, they do not scale well horizontally, making sharding (splitting data across multiple servers) challenging and potentially detrimental to performance.
- **ACID Compliance:** Unlike many other NoSQL databases, graph databases are ACID transaction compliant, ensuring that relationships between nodes remain intact and valid.

**Use Cases:**

- **Social Networking:** Ideal for applications that require quick access to interconnected data, such as finding friends or connections.
- **Routing and Spatial Applications:** Useful for modeling data in applications that need to find locations or calculate shortest paths.
- **Recommendation Engines:** Leverage the relationships between products to suggest options to customers based on their preferences.

**Limitations:**

- **Scaling Issues:** Not suitable for applications that require horizontal scaling.
- **Complex Updates:** Updating multiple nodes with a specific parameter can be complex and non-trivial.