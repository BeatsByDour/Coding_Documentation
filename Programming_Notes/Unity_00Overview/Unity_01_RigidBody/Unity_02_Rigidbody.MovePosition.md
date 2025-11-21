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

Verplaatst een kinematic Rigidbody naar een opgegeven positie tijdens de volgende physics update. Handig voor positionele controle zonder krachten.

## Signatuur

```
`void MovePosition(Vector3 position);`
```
## Parameters

- **position** – `Vector3` – De doelpositie in wereldruimte waar het object naartoe beweegt.

## Retourwaarde

- Geen returnwaarde.

## Gedrag / Opmerkingen

- Alleen bruikbaar op kinematic rigidbodies.
- Overschrijft velocity; conflicten mogelijk bij gebruik met AddForce.
- Best aanroepen in `FixedUpdate`.

## Voorbeeld

```
`rb.MovePosition(rb.position + Vector3.forward * speed * Time.fixedDeltaTime);`
```
## Gerelateerde functies

 [[Rigidbody.MoveRotation]] - [[Rigidbody.AddForce]] 

## Zie ook (concepten)

[[Concept – Physics update loop (FixedUpdate)]] 