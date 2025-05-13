# OpenMRS_SDK_RA
OpenMRS_Raikos_dev_TL
This project is a custom OpenMRS SDK setup with MySQL running in a Docker container. It provides a stable local development environment for further OpenMRS customization, module development, and system configuration.

## 🔧 Tech Stack
- **OpenMRS SDK**: Core EMR system
- **MySQL 5.7**: Database (via Docker container)
- **IntelliJ IDEA**: Development environment
- **Maven**: Dependency management

## 📦 Project Setup Instructions

1. **Clone this Repository**
   ```bash
   git clone https://github.com/your-username/OpenMRS_SDK_RA.git
   cd OpenMRS_SDK_RA
Start MySQL via Docker
docker run --name openmrs-mysql -e MYSQL_ROOT_PASSWORD=root -p 3306:3306 -d mysql:5.7
Create OpenMRS Database
docker exec -it openmrs-mysql mysql -u root -p
# Password: root
CREATE DATABASE OpenMRS_SDK_RA;
EXIT;
Ensure openmrs-runtime.properties is Present
Located at: ~/.OpenMRS/openmrs-runtime.properties
Example:

connection.url=jdbc:mysql://localhost:3306/OpenMRS_SDK_RA?autoReconnect=true&useUnicode=true&characterEncoding=UTF-8
connection.username=root
connection.password=root
connection.driver_class=com.mysql.jdbc.Driver
auto_update_database=true
Run the OpenMRS Server
mvn openmrs-sdk:run -DserverId=OpenMRS_SDK_RA
Access OpenMRS
Open a browser and go to:
http://localhost:8080/openmrs
If prompted for setup, follow the initialization wizard and recheck database connection settings.
📁 Directory Structure

.openmrs/: Runtime configuration (generated after setup)
/docker/: Optional Docker Compose files (add if needed)
/modules/: Place custom modules here if developing
setup-guide.pdf: Step-by-step setup instructions
👥 Collaborators

To contribute:

Fork the repository
Clone to your machine
Push feature branches
Submit Pull Requests
