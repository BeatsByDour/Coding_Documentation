
---

## type: bash component: coreutils category: bestanden kopiëren

## Component / Namespace

- Component: GNU coreutils
- Namespace: Bash shell

## Beschrijving

Kopieert bestanden of directories.

## Signatuur

```
cp [opties] bron doel
```

## Parameters

- **bron** – string – Bestand of map om te kopiëren.
- **doel** – string – Bestemming.
- **-r** – recursief kopiëren van directories.
- **-i** – vraagt bevestiging bij overschrijven.

## Retourwaarde

- Kopieert data naar de doelbestemming.

## Gedrag / Opmerkingen

- Zonder `-r` kun je geen directories kopiëren.

## Voorbeeld

```
cp -r assets/ backup/assets/
```

## Gerelateerde functies

- `mv`
- `rsync`

## Zie ook (concepten)

- Bestandsstructuren

---
