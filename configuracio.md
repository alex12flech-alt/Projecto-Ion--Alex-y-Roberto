# mkdocs.yml i deploy.yml

## mkdocs.yml

És el fitxer de configuració de MkDocs. Defineix el nom del lloc, el tema, el menú de navegació i els plugins.

```yaml
site_name: Chatbot de gestió de cites

theme:
  name: material

plugins:
  - search
  - glightbox
```

El plugin `glightbox` permet ampliar les imatges en fer-hi clic.

## deploy.yml

Es troba a `.github/workflows/deploy.yml`. És un workflow de GitHub Actions: cada vegada que fem `push` a la branca `main`, GitHub construeix la web i la publica a GitHub Pages.

```yaml
name: Deploy MkDocs

on:
  push:
    branches: [main]

permissions:
  contents: write

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: "3.12"
      - run: pip install -r requirements.txt
      - run: mkdocs gh-deploy --force
```

## Exemple de canvi en tots dos

Hem afegit el plugin `glightbox`.

A `mkdocs.yml` hem afegit el plugin:

```diff
 plugins:
   - search
+  - glightbox
```

A `requirements.txt` hem afegit la dependència perquè GitHub Actions la instal·li:

```diff
 mkdocs-material
+mkdocs-glightbox
```

A `deploy.yml` el pas `pip install -r requirements.txt` instal·la aquesta dependència automàticament abans de publicar.