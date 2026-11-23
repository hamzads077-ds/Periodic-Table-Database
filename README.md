# 🧪 Periodic Table Database

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Bash Script](https://img.shields.io/badge/Bash_Script-121011?style=for-the-badge&logo=gnu-bash&logoColor=white)
![freeCodeCamp](https://img.shields.io/badge/freeCodeCamp-0A0A23?style=for-the-badge&logo=freecodecamp&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

---


A relational database and interactive Bash command-line lookup utility for chemical elements, built as a certification project for the **freeCodeCamp Relational Database** curriculum.

---

## 📋 Overview

This project refactors and normalizes an existing PostgreSQL `periodic_table` database and provides an executable Bash script (`element.sh`) to query chemical element properties using an atomic number, chemical symbol, or element name.

---

## 🗄️ Database Schema

The database is normalized into three relational tables with enforced `PRIMARY KEY`, `FOREIGN KEY`, `UNIQUE`, and `NOT NULL` constraints:

1. **`elements`**
   - `atomic_number` (`INT`, Primary Key)
   - `symbol` (`VARCHAR`, Unique, Not Null)
   - `name` (`VARCHAR`, Unique, Not Null)

2. **`properties`**
   - `atomic_number` (`INT`, Primary Key, Foreign Key → `elements.atomic_number`)
   - `atomic_mass` (`DECIMAL`, Not Null)
   - `melting_point_celsius` (`NUMERIC`, Not Null)
   - `boiling_point_celsius` (`NUMERIC`, Not Null)
   - `type_id` (`INT`, Foreign Key → `types.type_id`, Not Null)

3. **`types`**
   - `type_id` (`INT`, Primary Key)
   - `type` (`VARCHAR`, Not Null — `metal`, `metalloid`, `nonmetal`)

---

## 🚀 Usage

### 1. Restore the Database
Rebuild the PostgreSQL database from the included SQL dump:
```bash
psql -U postgres < periodic_table.sql
chmod +x element.sh
./element.sh 1
./element.sh H
./element.sh Hydrogen
```

---

## 📊 Repository Stats

[![Stars](https://img.shields.io/github/stars/hamzads077-ds/Periodic-Table-Database?style=for-the-badge&logo=github&color=yellow)](https://github.com/hamzads077-ds/Periodic-Table-Database/stargazers)
[![Forks](https://img.shields.io/github/forks/hamzads077-ds/Periodic-Table-Database?style=for-the-badge&logo=github&color=blue)](https://github.com/hamzads077-ds/Periodic-Table-Database/network/members)
[![Views](https://komarev.com/ghpvc/?username=hamzads077-ds-Periodic-Table-Database&style=for-the-badge&color=brightgreen&label=VIEWS)](https://github.com/hamzads077-ds/Periodic-Table-Database
)
