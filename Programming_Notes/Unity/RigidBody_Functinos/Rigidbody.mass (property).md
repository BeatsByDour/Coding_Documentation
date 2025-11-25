# Rigidbody.mass  <!-- bv. Rigidbody.AddForce  -->

---
type: api-property  
component: Rigidbody  
category: physics

---
## Component / Namespace
- Component:   bv rigibody 
- Namespace: `UnityEngine`

## Beschrijving

De massa van het Rigidbody-object, in kilogram. Bepaalt hoe het object reageert op krachten en botsingen.

## Signatuur

```
float mass { get; set; }
```
## Parameters

- Geen (is een property).
## Retourwaarde

- `float` – De massa in kg.

## Gedrag / Opmerkingen

- Een hogere massa betekent meer weerstand tegen acceleratie en kracht.
- Beïnvloedt collision-resolutie en impuls-overdracht.

## Voorbeeld

```
rb.mass = 5.0f;
```
## Gerelateerde functies

[[Rigidbody.AddForce]]
## Zie ook (concepten)

[[Forces en beweging]]

