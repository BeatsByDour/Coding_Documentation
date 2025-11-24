---

---
 ---

type: api-function  
component: [[Rigidbody]]  
category: [[Physics]]

---

## Component / Namespace

- Component: [[Rigidbody]]
- Namespace: `UnityEngine`
## Beschrijving

Voegt een rotatiekoppel toe aan het Rigidbody-object, waardoor het roteert rond een as. Geschikt voor voertuigen en roterende mechanismen.

## Signatuur

```
void AddTorque(Vector3 torque, ForceMode mode = ForceMode.Force);
```
## Parameters

- **torque** –  [[Vector3]] – Het rotatiekoppelvector in wereldruimte.
- **mode** – [[Forcemode]] (optioneel) – De wijze waarop het koppel wordt toegepast (standaard: `ForceMode.Force`).

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

[[Rigidbody.Addforce]]

## Zie ook (concepten)

 [[Rotatie en koppel]]