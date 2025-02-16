# Kafka-Based Email Notification System 🚀
This is a Spring Boot application that integrates Apache Kafka and JavaMailSender to send emails both synchronously and asynchronously. It provides REST APIs to send emails directly or push email requests to Kafka for processing, ensuring high availability and scalability.

## 📌 Features
✅ Send emails synchronously using JavaMailSender.
✅ Push email requests to Kafka for asynchronous processing.
✅ Kafka Consumer automatically processes messages and sends emails.
✅ Configurable SMTP settings (Supports Gmail & other providers).
✅ Logging enabled to track Kafka messages and email delivery.
✅ Improved performance by decoupling email processing from API requests.
✅ Scalability – Can handle high loads efficiently with Kafka.

## 🏗️ Architecture Overview
Client (Postman / cURL)  --->  Spring Boot API  --->  Kafka Producer  --->  Kafka Topic (emailTopic)
                                                            |
                                                            |
                                                    Kafka Consumer  --->  JavaMailSender (SMTP)  --->  Email Delivery
Client Sends Email Request:

API receives the email request and processes it either synchronously or asynchronously.
Kafka Producer Pushes Messages to Topic:

If asynchronous mode is used, the request is sent to Kafka (emailTopic).
Kafka Consumer Reads Messages:

The consumer listens to emailTopic, fetches messages, and sends emails via JavaMailSender.
Email is Sent via SMTP:

The email is delivered using the SMTP protocol, ensuring secure and reliable transmission.
## 🛠️ Tech Stack
#### Java 20 (Spring Boot)
#### Apache Kafka (Producer & Consumer)
#### JavaMailSender (Email Service)
#### Postman/cURL (API Testing)
#### Maven (Dependency Management)
#### Zookeeper (Manages Kafka Broker Coordination)
#### SMTP (Email Protocol for Sending Emails)



