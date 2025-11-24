
---

type: unity-function  
component: Rigidbody  
category: physics

---

## Component / Namespace

- Component: Rigidbody
- Namespace: `UnityEngine`
    

## Beschrijving

Past een kracht toe op een specifiek punt op het Rigidbody. Dit veroorzaakt zowel lineaire beweging als rotatie (torque), afhankelijk van waar het punt zich bevindt t.o.v. het massamiddelpunt.

## Signatuur

csharp

```
void AddForceAtPosition(Vector3 force, Vector3 position, ForceMode mode = ForceMode.Force);
```

## Parameters

- **force** – [[Vector3]] – Krachtvector in wereldruimte.
- **position** – [[Vector3]] – Positie waar de kracht wordt toegepast (wereldruimte).
- **mode** – [[Forcemode]] (optioneel) – Hoe de kracht wordt toegepast (standaard `ForceMode.Force`).
    
## Retourwaarde

- Geen returnwaarde.

## Gedrag / Opmerkingen

- Aanroepen in `FixedUpdate`.
- Als het punt niet op het massamiddelpunt ligt, ontstaat automatisch torque.
- Ideaal voor realistische impact-simulaties (kogels, botsingen op specifieke punten).

## Voorbeeld

csharp

```
Vector3 hitPoint = collision.contacts[0].point; rb.AddForceAtPosition(Vector3.forward * 100f, hitPoint, ForceMode.Impulse);
```

## Gerelateerde functies

 [[Rigidbody.AddForce]] - [[Rigidbody.AddTorque]] - [[Rigidbody.AddExplosionForce]]

## Zie ook (concepten)

 [[Center of mass]] - [[Torque en momentum]] 