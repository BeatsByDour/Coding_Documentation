
---

type: unity-property  
component: [[Rigidbody]]  
category: [[Physics]]

---
## Component / Namespace

- Component: [[Rigidbody]]
- Namespace: `UnityEngine`

## Beschrijving

Bepaalt of het Rigidbody kinematic is (gecontroleerd door scripts/animaties) of dynamic (gecontroleerd door physics engine). Kinematic rigidbodies worden niet beïnvloed door krachten of zwaartekracht.

## Signatuur

csharp

```
bool isKinematic { get; set; }
```

## Parameters

- Geen (is een property).

## Retourwaarde

- [[Bool]] – `true` = kinematic, `false` = dynamic.

## Gedrag / Opmerkingen

- Kinematic rigidbodies: geen physics forces, wel collision detection.
- Gebruik voor platforms, deuren, of speler-controllers zonder physics.
- Switchen tijdens runtime kan (bijv. voor ragdoll-activatie).

## Voorbeeld

csharp

```
// Activeer ragdoll door kinematic uit te zetten rb.isKinematic = false;
```

## Gerelateerde functies

 [[Rigidbody.MovePosition]] - [[Rigidbody.MoveRotation]] 

## Zie ook (concepten)

 [[Kinematic vs dynamic rigidbodies]] - [[Ragdoll physics]] 