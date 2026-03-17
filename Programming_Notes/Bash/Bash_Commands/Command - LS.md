
---

## type: bash component: coreutils category: bestanden & directories

## Component / Namespace

- Component: GNU coreutils
- Namespace: Bash shell

## Beschrijving

Toont de inhoud van een directory. Je gebruikt `ls` om snel te zien welke bestanden en mappen aanwezig zijn, inclusief permissies, grootte en metadata wanneer je extra flags gebruikt.

## Signatuur

```
ls [opties] [pad]
```

## Parameters

- **pad** – string – Optioneel pad naar een directory of bestand.
- **-l** – toont uitgebreide lijstweergave (permissies, eigenaar, grootte).
- **-a** – toont _alle_ bestanden, inclusief verborgen (`.`‑prefix).
- **-h** – toont bestandsgroottes in menselijk formaat (bijv. 10K, 2M).

## Retourwaarde

- Print directory‑inhoud naar stdout.

## Gedrag / Opmerkingen

- Combineer flags voor meer detail (`ls -lah`).
- Verborgen bestanden zijn standaard niet zichtbaar.
- Werkt in elke shell.

## Voorbeeld

```
ls -lah /var/log
```

## Gerelateerde functies

- `tree`
- `find`

## Zie ook (concepten)

- Bestandspermissies
- Directory‑structuur in Linux
