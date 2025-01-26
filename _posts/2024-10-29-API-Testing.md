---
title: APIs in Software Testing
date: 2024-10-30 00:00:00 +0800
categories: [Learning]
tags: [api, api testing]     # TAG names should always be lowercase
---

# Table of Contents

1. [APIs](#apis)
   - [Short History of APIs](#short-history-of-apis)
   - [REST](#rest)
   - [Components of a REST API](#components-of-a-rest-api)
     - [1. Resources (Endpoints)](#1-resources-endpoints)
     - [2. HTTP Methods](#2-http-methods)
     - [3. Headers](#3-headers)
     - [4. Status Codes](#4-status-codes)
     - [5. Data (Payload)](#5-data-payload)
     - [6. Query Parameters and Path Parameters](#6-query-parameters-and-path-parameters)
     - [7. Authentication and Authorization](#7-authentication-and-authorization)
     - [8. Documentation](#8-documentation)
2. [Information API Creators Should Provide](#information-api-creators-should-provide)
3. [APIs in Software Testing](#apis-in-software-testing)


### APIs

## Short History of APIs
Application Programming Interface (API) is a technology used to facilitate communication or translate language between two distinct applications. APIs are widely used across various industries, with applications that vary based on accessibility, functionality, purpose, design/architecture, and more. APIs can also be categorized into two main groups based on their usage within an organization: Private and Public.

A good example which demonstrates what an API is in a simple way that doesn’t relate to the IT world would be:

>In a restaurant, you (the API consumer) choose a dish from the menu (the API documentation) and give your order, with any special requests, to the waiter (the API). The waiter communicates your order to the kitchen (the API server), where the chef (the server’s business logic) prepares the dish. Once ready, the waiter brings it back to your table.

The waiter acts as the "middleman," just like an API, transferring your request to the server and delivering the response back to you, all without you needing to interact with the kitchen directly.

## REST

I will primarily review APIs in the context of RESTful APIs due to their widespread use in web services today. 

**RE**presentational **S**tate **T**ransfer API (REST API) is a lightweight API which allows for software to communicate via [HTTP Methods](#2-http-methods) while data is processed in formats like JSON, XML, HTML etc.

Some benefits of REST APIs include ease of use, simplicity, and standardization, as users do not need to worry about the state or format of the data request. REST APIs are also easily scalable and stateless, meaning changes can be applied without users needing to track the data’s state.

Caching is another benefit of REST APIs, improving performance due to their lightweight nature.

## Components of a REST API
A REST API (Representational State Transfer API) consists of several key components that facilitate communication between clients (like web or mobile apps) and servers. Here’s a breakdown of its core components:

## 1. Resources (Endpoints)
Resources: Resources are the main entities of data that an API provides access to, such as **users**, **posts**, or **products**.

Endpoints: Each resource has a unique URL (endpoint) where it can be accessed, usually following a predictable structure, such as 
> https://api.example.com/users.

## 2. HTTP Methods

| HTTP Method | Description                                            | Example Request             |
|-------------|--------------------------------------------------------|------------------------------|
| **GET**     | Retrieve data from the server                         | `GET /users`                |
| **POST**    | Create new data on the server                         | `POST /users`               |
| **PUT**     | Update existing data                                   | `PUT /users/1`              |
| **PATCH**   | Apply partial updates to existing data                 | `PATCH /users/1`            |
| **DELETE**  | Remove data                                           | `DELETE /users/1`           |

## 3. Headers

| Header         | Description                                                         |
|----------------|---------------------------------------------------------------------|
| **Authorization** | Used for authentication tokens (e.g., API keys, JWT)               |
| **Content-Type**  | Specifies the format of the data sent (e.g., `application/json`)   |
| **Accept**        | Informs the server of the response format the client expects         |

## 4. Status Codes

| Status Code | Description                                   |
|-------------|-----------------------------------------------|
| **200**     | OK (success)                                 |
| **201**     | Created (successful creation of a resource)  |
| **400**     | Bad Request (client-side error)              |
| **401**     | Unauthorized (authentication required)       |
| **404**     | Not Found (resource not found)               |
| **500**     | Internal Server Error (server-side error)    |


## 5. Data (Payload)
Request Payload: Data sent by the client, especially for POST and PUT requests, often in JSON format.

Response Payload: Data returned by the server, which could include information about the requested resource, status, or error messages.

## 6. Query Parameters and Path Parameters
Query Parameters: Appended to the URL to filter or specify data, such as 
>https://api.example.com/users?role=admin.

Path Parameters: Variables within the endpoint path, usually representing specific resource IDs (e.g., GET /users/1 to access user with ID 1).
## 7. Authentication and Authorization
Definition: Security protocols that protect the API.

Types: Common methods include API keys, OAuth, JWT (JSON Web Tokens), and Basic Authentication to ensure only authorized users can access or modify resources.
## 8. Documentation
REST APIs are typically accompanied by documentation, detailing available resources, endpoints, parameters, expected responses, and error codes to guide developers.




## Information API Creators Should Provide

API creators should provide detailed information on the following:

| Information                     | Description                                                                                                         |
|----------------------------------|---------------------------------------------------------------------------------------------------------------------|
| **Business Use**                 | The specific business purposes for which the API can be used.                                                     |
| **API Location**                 | The URI (Uniform Resource Identifier) where the API can be accessed.                                              |
| **Input and Output Parameters**  | Including parameter names, message format (e.g., JSON or XML), and data types.                                    |
| **Network Protocol**             | The protocol required for API calls, such as HTTP/HTTPS, FTP/SFTP, or JMS.                                       |
| **API Security Requirements**     | Authentication and security protocols the client must follow, such as basic or multi-factor authentication, mTLS, input validation, IP filtering, etc. |
| **Service-Level Agreement (SLA)**| Details on performance commitments, such as response time, throughput, and availability.                           |
| **Rate Limits**                  | Specifications on the number of requests allowed per user or app within a given period.                           |
| **Legal or Business Constraints** | Information on usage constraints, including licensing terms, branding requirements, and any associated fees.       |
| **Documentation**                | Comprehensive resources to help users understand and implement the API effectively.                                |



### APIs in Software Testing

I will be expanding on this paragraph with real life examples of the role that QA or testers play when dealing with APIs.