# execution-environments

AAP/AWX execution environments built with [ansible-builder](https://ansible-builder.readthedocs.io/).

## Available Execution Environments

### oracle

Execution environment for Oracle Database automation.

**Included dependencies:**
- Collection: `community.general` (>=9.0.0)
- Python: `oracledb` (>=2.0.0) – official Oracle Python driver
- System: `libaio` / `libaio1` – required for Oracle Instant Client (thick mode)

**Build:**
```bash
cd oracle
ansible-builder build -f execution-environment.yml -t ee-oracle:latest
```

---

### mssql

Execution environment for Microsoft SQL Server automation.

**Included dependencies:**
- Collection: `community.general` (>=9.0.0)
- Python: `pymssql` (>=2.2.0) – SQL Server driver via FreeTDS
- System: `freetds-devel` / `freetds-dev` – required by pymssql

**Build:**
```bash
cd mssql
ansible-builder build -f execution-environment.yml -t ee-mssql:latest
```

---

## Prerequisites

Install `ansible-builder`:

```bash
pip install ansible-builder
```

## Base Image

Both execution environments use `quay.io/ansible/awx-ee:latest` as the base image, which is compatible with both AWX and Ansible Automation Platform (AAP).
