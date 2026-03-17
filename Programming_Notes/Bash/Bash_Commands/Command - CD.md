
---

## type: bash component: shell builtin category: navigatie

## Component / Namespace

- Component: Bash builtin
- Namespace: Bash shell

## Beschrijving

Wijzigt de huidige werkdirectory. Je gebruikt `cd` om door het bestandssysteem te navigeren.

## Signatuur

```
cd [pad]
```

## Parameters

- **pad** – string – Doelmap. Kan absoluut of relatief zijn.

## Retourwaarde

- Wijzigt de huidige directory van de shell.

## Gedrag / Opmerkingen

- `cd` zonder argument gaat naar de home directory.
- `cd -` springt terug naar de vorige directory.
- Relatieve paden zijn gebaseerd op de huidige directory.

## Voorbeeld

```
cd ~/projects/bash-scripts
```

## Gerelateerde functies

- `pwd`
- `ls`

## Zie ook (concepten)

- Absolute vs relatieve paden

---
