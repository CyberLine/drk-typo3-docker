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
- Im Browser http://127.0.0.1 aufrufen