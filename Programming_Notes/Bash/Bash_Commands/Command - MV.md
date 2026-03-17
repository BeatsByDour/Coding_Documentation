
---

## type: bash component: coreutils category: bestanden verplaatsen / hernoemen

## Component / Namespace

- Component: GNU coreutils
- Namespace: Bash shell

## Beschrijving

Verplaatst of hernoemt bestanden en directories.

## Signatuur

```
mv [opties] bron doel
```

## Parameters

- **bron** – string – Te verplaatsen bestand of map.
- **doel** – string – Nieuwe locatie of nieuwe naam.
- **-i** – vraagt bevestiging bij overschrijven.

## Retourwaarde

- Wijzigt locatie of naam van bestanden.

## Gedrag / Opmerkingen

- `mv bestand nieuwe_naam` is een rename.
- `mv bestand map/` verplaatst naar een directory.

## Voorbeeld

```
mv report.txt archive/report_2024.txt
```

## Gerelateerde functies

- `cp`
- `rm`

## Zie ook (concepten)

- Filesystem operations

---
