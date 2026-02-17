# AI Software Engineer Assignment (JS/TS)

This repository contains the solution for the Eskalate/A2SV AI Software Engineer technical assignment. The goal of this project is to demonstrate reliable environment setup, dependency management, and precise bug fixing.

## 🛠 Setup and Installation

### Prerequisites

- **Node.js**: Version 20.x or higher.
- **Docker**: For running the CI-style test environment.

### Local Installation

Dependencies in this project are pinned to exact versions to ensure build reproducibility. To install them:

1. Clone this repository.
2. Navigate to the root directory.
3. Run the following command:
   ```bash
   npm install
   ```

### How to build and run tests with Docker

1. Build docker image.
   ```bash
   docker build -t ai-assignment .
   ```
2. Run the following command for testing in docker:
   ```bash
   docker run ai-assignment
   ```

### How to run tests locally

- Run the following command for testing locally:
  ```bash
  npm test
  ```
