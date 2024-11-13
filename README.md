# DRK Typo3 Docker
Ergänzungsrepository, um die DRK Musterseiten unter Docker entwickeln zu können

### Installation

- Nach Abschluss des regulären Setups, wird der Inhalt dieses repos in den Hauptordner des Projektes kopiert
- diesen Codeschnipsel in der muster config hinzufügen `config/sites/muster/config.yaml`:
  ```yaml
  baseVariants:
  -
    base: 'http://127.0.0.1'
    condition: 'applicationContext == "Development"'
  ```
- docker compose aufrufen:
  ```bash
  docker compose up -d
  ```
- Datenbank anlegen und importieren:
  ```bash
  docker exec -i database mysql -u root -e "CREATE DATABASE IF NOT EXISTS typo3"
  docker exec -i database mysql typo3 -u root < ov-muster-dump.sql
  ```
- Im Browser http://127.0.0.1 aufrufen