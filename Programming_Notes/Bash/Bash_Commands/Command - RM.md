
---

## type: bash component: coreutils category: verwijderen

## Component / Namespace

- Component: GNU coreutils
- Namespace: Bash shell

## Beschrijving

Verwijdert bestanden of directories. **Onomkeerbaar**.

## Signatuur

```
rm [opties] pad
```

## Parameters

- **pad** – string – Bestand of directory.
- **-r** – recursief verwijderen.
- **-f** – force, geen waarschuwingen.

## Retourwaarde

- Verwijdert data permanent.

## Gedrag / Opmerkingen

- `rm -rf` is krachtig maar gevaarlijk.
- Geen prullenbak: weg = weg.

## Voorbeeld

```
rm -rf build/
```

## Gerelateerde functies

- `rmdir`
- `trash-cli`

## Zie ook (concepten)

- Filesystem safety

---
