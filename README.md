🔹 Project Overview
A Spring Boot REST API for file upload and download.

Demonstrates handling multipart requests, saving files to a configurable directory, and serving them back with proper headers.

🔹 Tech Stack
Spring Boot (Web starter for REST APIs)

Spring MVC Multipart support

Java NIO Files API for storage

Optional: Spring Security (if you want to secure endpoints later)

🔹 Features
Upload files via POST /files/upload using form-data (key = file).

Download files via GET /files/download/{fileName}.

Configurable upload directory via application.yml.

MIME type detection for downloads.

Path traversal protection (ensures files stay inside the storage directory).

Custom exception handling (FileStorageException) for cleaner error responses.

🔹 Configuration
In application.yml:

yaml
server:
  port: 7071

spring:
  servlet:
    multipart:
      enabled: true
      max-file-size: 10MB
      max-request-size: 10MB

file:
  upload-dir: uploads
🔹 Usage
Upload:

bash
POST http://localhost:7071/files/upload
Body: form-data
Key: file (type = File)
Value: select a file (e.g., image.jpeg)
Download:

bash
GET http://localhost:7071/files/download/{fileName}
