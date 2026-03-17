
---

## type: bash component: coreutils category: directories

## Component / Namespace

- Component: GNU coreutils
- Namespace: Bash shell

## Beschrijving

Maakt een nieuwe directory aan. Je gebruikt `mkdir` om projectmappen, logs, outputfolders… te creëren.

## Signatuur

```
mkdir [opties] directory
```

## Parameters

- **directory** – string – Naam van de nieuwe map.
- **-p** – maakt ook ontbrekende bovenliggende mappen aan.

## Retourwaarde

- Maakt een directory aan op het bestandssysteem.

## Gedrag / Opmerkingen

- `mkdir -p a/b/c` voorkomt fouten als mappen al bestaan.

## Voorbeeld

```
mkdir -p src/modules/utils
```

## Gerelateerde functies

- `rmdir`
- `rm -r`

## Zie ook (concepten)

- Directory‑structuren

---
