# Hello API Documentation

Welcome to the official documentation for the **Hello API**, a fictional RESTful web service designed to demonstrate professional API documentation practices.

## 📚 What's Included

 ✅ Getting Started Guide
 ✅ API Reference Documentation
 ✅ OpenAPI Specification (Swagger)
 ✅ Changelog & Versioning
 ✅ Best Practices for Writing Dev Docs

> 🖋️ *Created and maintained by a technical writer for demonstration purposes.*

## 🔧 Getting Started

See [`getting-started.md`](./getting-started.md) for setup and usage.

## 🔍 API Reference

See [`api-reference.md`](./api-reference.md) for endpoint details.

## 📄 OpenAPI Spec

See [`openapi.yaml`](./openapi.yaml) to view or import this API spec into Swagger UI or Postman.

getting-started.md
markdown
Copy code
# Getting Started with Hello API

This guide walks you through how to interact with the Hello API in under 5 minutes.

## 1. Requirements

- `curl` or Postman
- Internet connection

## 2. Base URL

https://api.hello-world.dev/v1

bash
Copy code

## 3. Quick Test

```bash
curl https://api.hello-world.dev/v1/greet?name=M'Shai
Response:

json
Copy code
{
  "message": "Hello, M'Shai!"
}
4. Authentication
This version of Hello API does not require authentication.

yaml
Copy code

---

#### `api-reference.md`

```markdown
# Hello API – Reference Guide

## GET `/greet`

Returns a friendly greeting.

### Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `name` | `string` | No | Name to include in the greeting |

### Example Request

```bash
curl https://api.hello-world.dev/v1/greet?name=Sam
Example Response
json
Copy code
{
  "message": "Hello, Sam!"
}
GET /status
Returns API status.

Example Request
bash
Copy code
curl https://api.hello-world.dev/v1/status
Example Response
json
Copy code
{
  "status": "OK",
  "timestamp": "2025-07-11T02:00:00Z"
}
yaml
Copy code

---

#### `changelog.md`

```markdown
# Changelog

All notable changes to the Hello API documentation will be documented here.

## [1.0.0] – 2025-07-11

### Added

- Initial documentation structure
- `greet` and `status` endpoints
- OpenAPI YAML file
- Getting started guide

---
openapi.yaml
yaml
Copy code
openapi: 3.0.3
info:
  title: Hello API
  description: A simple demo API for technical writing portfolios
  version: 1.0.0

paths:
  /greet:
    get:
      summary: Returns a greeting
      parameters:
        - in: query
          name: name
          schema:
            type: string
          required: false
          description: Name to include in the greeting
      responses:
        '200':
          description: A greeting message
          content:
            application/json:
              schema:
                type: object
                properties:
                  message:
                    type: string

  /status:
    get:
      summary: Returns the status of the API
      responses:
        '200':
          description: API status
          content:
            application/json:
              schema:
                type: object
                properties:
                  status:
                    type: string
                  timestamp:
                    type: string
                    format: date-time
---
