
---

## type: bash component: coreutils category: bestanden lezen

## Component / Namespace

- Component: GNU coreutils
- Namespace: Bash shell

## Beschrijving

Leest en toont de inhoud van een bestand. Je gebruikt `cat` om snel tekstbestanden te bekijken of bestanden samen te voegen.

## Signatuur

```
cat [opties] bestand
```

## Parameters

- **bestand** – string – Bestandsnaam.
- **-n** – toont regelnummers.

## Retourwaarde

- Print de inhoud van het bestand naar stdout.

## Gedrag / Opmerkingen

- Voor grote bestanden is `less` vaak beter.
- Kan meerdere bestanden achter elkaar tonen.

## Voorbeeld

```
cat -n script.sh
```

## Gerelateerde functies

- `less`
- `head`
- `tail`

## Zie ook (concepten)

- Standaarduitvoer (stdout)

---
