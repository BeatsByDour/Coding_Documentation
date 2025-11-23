
---

type: unity-function  
component: [[Rigidbody]]  
category: [[Physics]]

---

## Component / Namespace

- Component: [[Rigidbody]]
- Namespace: `UnityEngine`

## Beschrijving

Voegt een kracht toe in de lokale coördinatenruimte van het Rigidbody, in plaats van wereldruimte. Handig voor voertuigen of objecten die altijd in hun eigen "vooruit"-richting moeten versnellen, ongeacht hun globale oriëntatie.

## Signatuur

csharp

```
void AddRelativeForce(Vector3 force, ForceMode mode = ForceMode.Force);
```

## Parameters

- **force** – [[Vector3]] – Krachtvector in lokale ruimte (bijv. `Vector3.forward` = vooruit t.o.v. object).
- **mode** – [[Forcemode]] (optioneel) – Bepaalt hoe de kracht wordt toegepast (standaard `ForceMode.Force`).

## Retourwaarde

- Geen returnwaarde.

## Gedrag / Opmerkingen

- Aanroepen in `FixedUpdate` voor stabiele physics.
- Werkt alleen op niet-kinematic rigidbodies.
- Ideaal voor voertuigbewegingen (forward thrust, strafing).

## Voorbeeld

csharp

```
rb.AddRelativeForce(Vector3.forward * 20f);
```

## Gerelateerde functies

[[Rigidbody.AddForce]] - [[Rigidbody.AddRelativeTorque]] 

## Zie ook (concepten)

 [[Lokale vs wereldruimte]] - [[Forces en beweging]]