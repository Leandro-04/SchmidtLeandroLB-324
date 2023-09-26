# LB 324

## Aufgabe 2
Installation des pre-commit-Pakets:

Verwenden Sie den Befehl pip install pre-commit, um das pre-commit-Tool zu installieren. Dies setzt voraus, dass Sie bereits Python und Pip auf Ihrem System installiert haben.
Konfigurationsdatei für pre-commit erstellen:

Im Hauptverzeichnis Ihres Projekts erstellen Sie eine Datei namens .pre-commit-config.yaml. In diese Datei fügen Sie die Hooks ein, die Sie verwenden möchten. Hier der Code für die Automatisierung usw:


repos:
  - repo: https://github.com/ambv/black
    rev: 23.9.1
    hooks:
      - id: black
        name: Auto-format code on commit
        language_version: python3.11.4

  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v2.3.0
    hooks:
      - id: check-yaml
      - id: end-of-file-fixer
      - id: trailing-whitespace

  - repo: https://github.com/psf/black
    rev: 22.10.0
    hooks:
      - id: black

  - repo: local
    hooks:
      - id: pytest-check
        stages: [commit]
        types: [python]
        name: pytest-check
        entry: python -m pytest
        language: system
        pass_filenames: false
        always_run: true


Installation der Hooks:

Um die in .pre-commit-config.yaml definierten Hooks in Ihrem Git-Repository zu installieren, führen Sie den Befehl pre-commit install im Hauptverzeichnis Ihres Projekts aus. Dadurch wird sichergestellt, dass die Hooks jedes Mal ausgeführt werden, wenn Sie versuchen, einen Commit oder Push durchzuführen (abhängig von der Konfiguration).

## Aufgabe 4
Erklären Sie hier, wie Sie das Passwort aus Ihrer lokalen `.env` auf Azure übertragen.
