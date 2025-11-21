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

Voegt een kracht toe aan het Rigidbody-object waardoor het accelereert volgens de physics engine. Wordt gebruikt om natuurlijke bewegingen zoals duwen of springen te simuleren.

## Signatuur

```
`void AddForce(Vector3 force, ForceMode mode = ForceMode.Force);`
```
## Parameters

- **force** – `Vector3` – De krachtvector in wereldcoördinaten.
    
- **mode** – `ForceMode` (optioneel) – De wijze waarop de kracht wordt toegepast (standaard: `ForceMode.Force`).
## Retourwaarde

- Geen returnwaarde.
## Gedrag / Opmerkingen

- Aanroepen tijdens `FixedUpdate` voor stabiele physics.
- Werkt alleen op niet-kinematic rigidbodies.
- Kan conflicteren met `MovePosition` omdat die positie rechtstreeks aanpast.

## Voorbeeld

```
`rb.AddForce(transform.forward * 500f);`
```

## Gerelateerde functies

 [[Rigidbody.AddRelativeForce]] - [[Rigidbody.MovePosition]] - [[Rigidbody.AddTorque]] 

## Zie ook (concepten)

[[Concept – Forces en beweging]] - [[Concept – Physics update loop (FixedUpdate)]] 