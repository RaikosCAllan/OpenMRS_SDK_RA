# HNGV OpenMRS 2.4.3 Setup

This repository documents the development and deployment of the OpenMRS Platform 2.4.3 instance for the National Hospital (HNGV) in Timor-Leste. This build is intended for secure, offline use, without any patient data. It is modular, extensible, and designed for stability in low- and middle-income country (LMIC) healthcare environments.

---

## 🚀 System Overview

* **Platform**: OpenMRS Core 2.4.3
* **UI**: LegacyUI 1.8.4
* **Java**: Temurin 8 (JDK 1.8)
* **Web Server**: Apache Tomcat 9
* **Database**: MySQL 5.7 (running in Docker container `openmrs-mysql`)
* **Operating System**: macOS (development), Windows Server (target deployment)

---

## 📁 Folder Structure

```
openmrs-hngv/
├── README.md                # Project documentation
├── scripts/                 # Backup & restore scripts
│   ├── backup_openmrs.sh
│   └── restore_openmrs.sh
├── modules/                 # All required .omod modules
│   ├── legacyui-1.8.4.omod
│   └── ...
├── config/                  # Configuration templates
│   └── openmrs-server.properties
├── notes/                   # Development and install notes
│   ├── build-log.md
│   └── module-compatibility.md
```

---

## ✅ Installed Modules

```
legacyui-1.8.4.omod
coreapps-1.34.0.omod
registrationapp-1.24.0.omod
htmlformentry-4.1.0.omod
... (see /modules for full list)
```

---

## 📌 Runtime Configuration

Runtime file is generated during setup at:

```
~/.OpenMRS/openmrs-runtime.properties
```

> Do **not** version-control this file. It contains DB credentials.

---

## 🔄 Backup and Restore

Use the provided scripts in the `/scripts` folder to backup and restore the database and runtime environment. These interact with the `openmrs-mysql` Docker container.

---

## 🧱 Rebuilding on Windows Server

Documentation will be added in `notes/windows-install-guide.md` to help replicate this build on the production server.

---

## 📋 To Do

---

## 🔐 License

This project inherits the OpenMRS Public License. All .omod files remain under their respective licenses. No patient data is tracked in this repository.

---

## 🤝 Maintainer

**Raikos Allan**
Developer & Implementation Lead, Timor-Leste

---

For questions or collaboration requests, contact via GitHub Issues or secure internal channels.

