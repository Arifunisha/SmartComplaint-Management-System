# Smart Complaint & Service Management Platform

A full-stack microservice-based complaint and service management platform built using Java, Spring Boot, ReactJS, MySQL, JWT, and OAuth2.

## Project Overview

The platform allows customers to raise and track complaints, employees to manage assigned service requests, managers to assign and monitor complaints, and administrators to manage users and system operations.

## Architecture

```text
ReactJS Frontend
        |
        v
   API Gateway
        |
        v
   Eureka Server
        |
        +-------------------+
        |         |         |
        v         v         v
 User Service  Complaint  Assignment
                Service     Service
        |          |          |
        v          v          v
     MySQL      MySQL       Feign