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

Leest of stelt de huidige lineaire snelheid van het Rigidbody in wereldruimte in. Kan gebruikt worden om directe snelheidsaanpassingen te doen.

## Signatuur

```
`Vector3 velocity { get; set; }`
```
## Parameters

- Geen parameters (property).
## Retourwaarde

- `Vector3` – Huidige snelheid van het object.
## Gedrag / Opmerkingen

- Rechtstreeks aanpassen negeert krachten en resulteert in onmiddellijke snelheidsverandering.
- Meestal lezen in `Update`, wijzigen in `FixedUpdate`.
## Voorbeeld

```
`rb.velocity = new Vector3(0, 5, 0);`

```
## Gerelateerde functies

[[Rigidbody.AddForce]]
## Zie ook (concepten)

[[Concept – Snelheid en versnelling]] 