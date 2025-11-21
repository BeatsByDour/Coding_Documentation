---

---
  
---

type: api-function  
component: Rigidbody  
category: physics

---

## Component / Namespace

- Component: [[Programming_Notes/Unity_00Overview/Rigidbody]]
- Namespace: `UnityEngine`
## Beschrijving

Voegt een rotatiekoppel toe aan het Rigidbody-object, waardoor het roteert rond een as. Geschikt voor voertuigen en roterende mechanismen.

## Signatuur

```
`void AddTorque(Vector3 torque, ForceMode mode = ForceMode.Force);`
```
## Parameters

- **torque** – `Vector3` – Het rotatiekoppelvector in wereldruimte.
- **mode** – `ForceMode` (optioneel) – De wijze waarop het koppel wordt toegepast (standaard: `ForceMode.Force`).

## Retourwaarde

- Geen returnwaarde.

## Gedrag / Opmerkingen

- Gebruik in `FixedUpdate`.
- Werkt alleen op niet-kinematic rigidbodies.

## Voorbeeld


```
`rb.AddTorque(Vector3.up * 50f);`
```

## Gerelateerde functies

[[Rigidbody.AddForce]]

## Zie ook (concepten)

 [[Concept – Rotatie en koppel]]