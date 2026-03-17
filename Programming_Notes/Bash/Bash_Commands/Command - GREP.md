
---

## type: bash component: grep category: zoeken in tekst

## Component / Namespace

- Component: GNU grep
- Namespace: Bash shell

## Beschrijving

Zoekt naar tekstpatronen in bestanden of output. Je gebruikt `grep` om snel regels te vinden die een bepaald woord of regex bevatten.

## Signatuur

```
grep [opties] patroon [bestand]
```

## Parameters

- **patroon** – string/regex – Tekst of patroon om te zoeken.
- **bestand** – string – Doelbestand.
- **-i** – case‑insensitive zoeken.
- **-r** – recursief zoeken in directories.
- **-n** – toont regelnummers.

## Retourwaarde

- Print alle regels die matchen.

## Gedrag / Opmerkingen

- Combineer met pipes (`|`) om output te filteren.
- Regex‑ondersteuning maakt het extreem krachtig.

## Voorbeeld

```
grep -rin "error" ./src
```

## Gerelateerde functies

- `awk`
- `sed`
- `find`

## Zie ook (concepten)

- Regular expressions
- Pipes & filters

---
