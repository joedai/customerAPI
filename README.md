# Customer REST API

This API allows the client to 
* Create customers in one single request
* Update a single customer
* Delete a single customer
* Retrieve a customer
* List all customers

# Prerequisites
Database is required to get the APIs running

If you are using MySQL, run the following script to create the customer table

```
CREATE SCHEMA `customer_schema` ;


CREATE TABLE `customer_schema`.`customer` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `first_name` VARCHAR(45) NULL,
  `last_name` VARCHAR(45) NULL,
  `address` VARCHAR(45) NULL,
  PRIMARY KEY (`id`));
```

