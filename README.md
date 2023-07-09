# starting-page-infra

Ansible playbooks for provisioning my [starting-page](https://github.com/christianwaldmann/starting-page) application.

## Prerequisites

1. Copy [hosts.sample](hosts.sample) to `hosts` and fill in the placeholders
2. Copy [.env.sample](.env.sample) to `.env` and fill in the placeholders

## Usage

### Setup server

```zsh
ansible-playbook setup_server.yml -i hosts
```

### Deploy application

```zsh
ansible-playbook deploy.yml -i hosts
```

### Upload and overwrite database

Copy your database into the same directory as the ansible playbook and name it `db.sqlite3`. To copy it onto the server and overwrite the existing database, run:

```zsh
ansible-playbook upload_and_overwrite_database.yml -i hosts
```

### Download database

```zsh
ansible-playbook download_database.yml -i hosts
```

This download the database to `./backups`.

### Remove certificate

```zsh
ansible-playbook remove_certificate.yml -i hosts
```
