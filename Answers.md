1. Explain the relationship between the "Product" and "Product_Category" entities from the above diagram.
Answer. The diagram shows a relational database schema for an e-commerce system. The two entities are:
Product: This entity represents a physical product that can be sold. It has attributes such as id, name, description (desc), SKU (stock keeping unit), category_id (foreign key), inventory_id (foreign key), price, discount_id (foreign key), created_at, modified_at, and deleted_at.
Product_Category: This entity represents a category that products can be classified into. It has attributes such as id, name, description (desc), created_at, modified_at, and deleted_at.
The relationship between these two entities is one-to-many. A product can belong to one category (represented by the category_id foreign key in the Product table), but a category can have many products. This is reflected by the fact that the product_category table does not have a foreign key referencing the product table.

2. How could you ensure that each product in the "Product" table has a valid category assigned to it?
Answer. There are two main approaches to ensure each product has a valid category assigned:
Database Constraints:
Foreign Key Constraint: This is the most common approach. You can define a foreign key constraint on the category_id column in the Product table. This constraint would reference the primary key (id) of the Product_Category table. This enforces data integrity by ensuring that the category_id in a product record always points to an existing category in the Product_Category table.
Application Logic:
Validation on Insert/Update: During the process of adding or updating a product, you can implement application-side validation. This validation would check if the provided category_id exists in the Product_Category table before creating or updating the product record. This approach offers more flexibility but requires code implementation.
