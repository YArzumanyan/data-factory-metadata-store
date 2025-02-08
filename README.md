# Metadata Store

The Metadata Store is a simple, central repository for managing pipeline configurations and metadata for the data factory. This service stores the "recipes" for pipelines, which reference datasets and scripts, and uses JSON-LD.

## Prerequisites

- **Java Development Kit (JDK) 11 or higher**
- **Maven** (or Gradle if you prefer)

## Getting Started

### Clone the Repository

```bash
git clone https://github.com/YArzumanyan/data-factory-metadata-store.git
cd data-factory-metadata-store
```

### Build the Project

If you are using Maven:

```bash
mvn clean install
```

### Run the Application

You can run the application directly using Maven:

```bash
mvn spring-boot:run
```

Alternatively, you can run the generated JAR file:

```bash
java -jar target/metadata-store-0.0.1-SNAPSHOT.jar
```

The application will start on the default port (usually `8080`). You can change this in the `src/main/resources/application.properties` file if needed.

## API Endpoints

Here are some basic endpoints available in this simple version:

- **Create/Update Pipeline**
  - **Endpoint:** `POST /pipelines`
  - **Description:** Accepts a JSON file representing the pipeline configuration.
  - **Example Payload:**
    ```json
    {
      "pipelineId": "pipeline-123",
      "uri": "http://example.com/data",
      "description": "A sample pipeline configuration",
      "@context": "http://schema.org"
    }
    ```

- **Retrieve Pipeline by ID**
  - **Endpoint:** `GET /pipelines/{pipelineId}`
  - **Description:** Fetches the pipeline configuration for the specified pipeline ID.

## Configuration

Configuration settings are managed in the `src/main/resources/application.properties` file. This includes server settings, database connections (if applicable), and other application-specific properties.