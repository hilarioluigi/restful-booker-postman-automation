# Restful Booker
Automated test suite for the [**Restful Booker API**](https://restful-booker.herokuapp.com/apidoc/index.html ), covering CRUD operations, authentication, and data validation checks.

## 🛠️ Tools
1. **API Testing Tool:** Postman
2. **Script:** JavaScript
3. **CI/CD:** Newman
4. **Version Control:** Github

## 🧪 Test Coverage
|Test          |Description|
|--------------|-----------|
|Performance   |Validates that response times are within acceptable limits|
|Status code   |Ensures status codes match expected results|
|Schema        |Verifies that all required attributes are present in the JSON response|
|Business Logic|Confirms that created data can be retrieved and updated correctly (End-to-End flow).|
|Security      |Validates authentication tokens for restricted endpoints (Delete/Update).|

## 📥 Installation & Setup
### Prerequisites
- **Node.js 24+:** [Download here](https://nodejs.org/en/download) (Check version with ```node -v```)
- **Newman:**
    ```bash
    npm install -g newman
    ```
    *Note: Required for **Newman CLI** execution.*
### Installation
1. Clone the repository:
    ```bash
    git clone https://github.com/hilarioluigi/restful-booker-postman-automation.git
    ```
2. Navigate to the project folder:
    ```bash
    cd restful-booker-postman-automation
    ```
## 🚀 Execution
### Option 1: Newman CLI
```bash
newman run Restful-Booker.postman_collection.json \
-e Restful-Booker.postman_environment.json \
--env-var "username=<YOUR_USERNAME>" \
--env-var "password=<YOUR_PASSWORD>"
```
*Note: You can find the default credential in the [API Documentation](https://restful-booker.herokuapp.com/apidoc/index.html#api-Auth-CreateToken).*

### Option 2: Postman GUI
1. Open **Postman.**
2. Click the **Import** button.
3. Drag and drop the ```Restful-Booker.postman_collection.json``` and ```Restful-Booker.postman_environment.json``` files.
4. Select the **Restful-Booker** environment in the top-right corner.
5. Update the ```username``` and ```password``` variables in the environment settings.
6. Click the **View more actions** and select **Run**.
7. click **Start run**.

## 🤖 CI/CD Integration
This project uses **GitHub Actions** to automatically execute the test suite on every push to the ```main``` branch. Credentials are securely managed via **GitHub Secrets**.