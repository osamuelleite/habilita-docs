# Primeiros passos (para toda a equipe)

## A ideia em uma frase

Cada página do site é um arquivo `.md` dentro de `docs/`. O `mkdocs.yml` diz a ordem do menu. O MkDocs junta tudo e monta o site.

## Instalar (uma vez)

```
python --version
python -m pip install -r requirements-docs.txt
copy openapi.yaml docs\openapi.yaml
```

(No Mac: `python3` no lugar de `python` e `cp openapi.yaml docs/openapi.yaml`.)

## Trabalhar (todo dia)

```
python -m mkdocs serve
```

Abrir http://127.0.0.1:8000 · editar o `.md` · salvar · conferir no navegador · `Ctrl + C` para desligar.

## Regras da equipe

1. Escreva só dentro de `docs/`.
2. Página nova = arquivo `.md` **e** linha no `nav:` do `mkdocs.yml`.
3. Apague a caixa "Sobre esta página" quando a página estiver pronta.
4. Nada de nome real, CPF ou empresa identificável.
5. Antes de enviar ao GitHub, rode `python -m mkdocs build --strict` — tem que terminar sem erro.
