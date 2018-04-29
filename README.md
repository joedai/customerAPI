# Customer REST API


# Features

## Capabilities
This API allows the client to 
* Create customers in one single request
* Update a single customer
* Delete a single customer
* Retrieve a customer
* List all customers

## Contiditonal Get
The API allows the client to do a conditional GET by providing the *If-Modified-Since* HTTP header.

This feature is useful for mobile apps as it saves bandwidth by returning no body content.


## Periodic Synchronisation
For clients who needs to synchronise the customers periodically, they can add the *lastModified* query parameter to the GET end point to get the incremental changes.

e.g.
```
GET /api/customers?lastModified=Sat, 28 Apr 2018 16:58:35 GMT
```

This parameter will be used by the server to check if there are any changes after the specified time, including:
* New customers stored
* Any updates to existing customers
* Any deletion to existing customers(the *deleted* field will be *true*)



# To Run The APIs
Database is required to get the APIs running

Make sure you update the database configuration in the *Global Mule Configuration Elements*

If you are using MySQL, run the following script to create the customer table

```
CREATE SCHEMA `customer_schema` ;


CREATE TABLE `customer_schema`.`customer` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `first_name` VARCHAR(45) NULL,
  `last_name` VARCHAR(45) NULL,
  `address` VARCHAR(45) NULL,
  `last_modified` DATETIME NULL,
  `deleted` VARCHAR(5) NULL DEFAULT 'false'
  PRIMARY KEY (`id`));


