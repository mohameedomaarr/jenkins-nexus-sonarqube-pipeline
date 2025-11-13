# Prerequisites

Before running the application, ensure the following tools are installed:

Java Development Kit (JDK): Version 17 or 21

Apache Maven: Version 3.9

MySQL: Version 8

Optional tools for additional features:

Tomcat or any compatible Servlet container (for WAR deployment)

Memcached (for caching)

RabbitMQ (for messaging queues)

Elasticsearch (for search functionality)

Technologies Used

The project leverages a combination of modern Java frameworks and libraries:

Spring Framework

Spring MVC (Web application framework)

Spring Security (Authentication and authorization)

Spring Data JPA (Database access and ORM)

Maven (Build automation and dependency management)

JSP (JavaServer Pages for dynamic web views)

Tomcat (Servlet container)

MySQL (Relational database)

Memcached (Caching)

RabbitMQ (Message broker for asynchronous communication)

Elasticsearch (Advanced search and analytics)

# Database Setup

This project uses MySQL as the primary database.

The database dump is available at:

/src/main/resources/db_backup.sql


To import the database:

mysql -u <username> -p accounts < db_backup.sql


Replace <username> with your MySQL user. The accounts database will be created and populated from the dump file.

# Project Structure

src/main/java – Java source code

src/main/resources – Configuration files, SQL dump, and static resources

src/main/webapp – JSP views and web resources

pom.xml – Maven project configuration (dependencies and build plugins)

Building and Running the Project

Build the project using Maven:

mvn clean install


# Run tests:

mvn test


# Deploy the WAR file (if using Tomcat):

Locate the WAR file in target/ folder.

Deploy it to your Tomcat webapps folder.

Start Tomcat and access the application via http://localhost:8080/vprofile.

# Additional Notes

Ensure Nexus repositories are configured in settings.xml if using private dependencies.

For SonarQube analysis, refer to the Jenkins CI/CD pipeline for integrated code quality checks.

Caching, messaging, and search features require Memcached, RabbitMQ, and Elasticsearch to be running.