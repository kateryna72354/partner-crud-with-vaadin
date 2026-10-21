# Customer CRUD with Vaadin

A Java application for managing customers, built with Spring Boot, Vaadin,
Spring Data JPA and H2.

## Requirements
- JDK 21, with JAVA_HOME pointing to the JDK.
- Internet access for the first run to download dependencies and frontend tools.
- Port 8080 available. Stop any other local application using that port first.

The repository includes Maven and Gradle wrappers, so a separate Maven or
Gradle installation is not needed. The commands below use Maven.

## Run locally
From the repository root on Windows:
```powershell
.\mvnw.cmd spring-boot:run
```

On Linux or macOS:
```sh
sh mvnw spring-boot:run
```

Wait for the application startup message, then open http://localhost:8080.
The first startup may take longer while dependencies are downloaded.
Keep the terminal open; press Ctrl+C to stop.

## Use the application
- **Create:** click **New customer**, enter first and last name, then **Save**.
- **Read:** view the customers in the grid.
- **Update:** select a customer in the grid, change the fields, then **Save**.
- **Delete:** select an existing customer and click **Delete**.
- **Filter:** enter the beginning of a last name. Matching ignores letter case.
  Clear the filter to display all customers.

Sample customers are inserted at startup. With the current default embedded
H2 configuration, changes are temporary and reset when the application restarts.

## Project structure
- `CrudWithVaadinApplication`: starts Spring Boot and inserts sample customers.
- `Customer`: customer entity.
- `CustomerRepository`: database access and last-name prefix search.
- `MainView`: customer grid, filter and New customer button.
- `CustomerEditor`: editing fields and Save, Cancel and Delete actions.
- `doc/`: screenshots of the running application, customer creation, filtering
  and startup output.

Java sources are in `src/main/java/com/example/crudwithvaadin/`.

## Run tests
Windows:
```powershell
.\mvnw.cmd test
```

Linux or macOS:
```sh
sh mvnw test
```
