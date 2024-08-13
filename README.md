# Odoo Open Upgrade Migration Tools

This project help to run odoo open upgrade using docker.
Docker compose is used to specify each container for each migration steps.
Each container service is build using dockefile in each `version` folder.
ex: `12.0/` will contain dockefile needed for 12.0 odoo migration.

## Installation
Simply clone this repo and make sure both `docker` and `docker compose` is installed.
```sh
git clone https://github.com/mcimam/odoo_open_upgrade_docker.git
```


## How to use
1. Init container

    Create container from compose
    ``` sh
    ./migrate
    ```

2. Load database

    Load database to docker container. For example suppose you have dump.sql as your backup file.
    ``` sh
    ./migrate loaddb dump.sql
    ```

3. Run Migration

    Run migration and specify your source and target version.
    ``` sh
    ./migrate migrate 11.0 16.0
    ```

5. Restore Migration

    Restore migrated database to `.sql` or `.dump` file
    ``` sh
    ./migrate dump new_dump.sql
    ```

## License
This repository is licensed under `AGPL-3.0`.

However tools that being used in this software can be under different licenses :
- `Odoo` use `LGPLv3`
- `Odoo Open upgrade` use `AGPLv3` 