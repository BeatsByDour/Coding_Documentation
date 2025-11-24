
---

type: unity-property  
component: [[Rigidbody]]  
category: [[Physics]]

---

## Component / Namespace

- Component: [[Rigidbody]]
- Namespace: `UnityEngine`

## Beschrijving

Leest of stelt de hoeksnelheid (angular velocity) van het Rigidbody in, gemeten in radialen per seconde. Bepaalt hoe snel het object roteert rond zijn assen.

## Signatuur

csharp

```
Vector3 angularVelocity { get; set; }
```

## Parameters

- Geen (is een property).

## Retourwaarde

- [[Vector3]] – Hoeksnelheid in rad/s, per as (x, y, z).  

## Gedrag / Opmerkingen

- Directe toekenning overschrijft torque-effecten.
- Gebruik in `FixedUpdate` voor aanpassingen.
- Handig voor spin-effecten of rotatiebegrenzing.

## Voorbeeld

csharp

```
// Constant draaien rond Y-as rb.angularVelocity = new Vector3(0, 5f, 0);
```

## Gerelateerde functies

 [[Rigidbody.AddTorque]] - [[Rigidbody.maxAngularVelocity]] 

## Zie ook (concepten)

 [[Rotatie en koppel]] - [[Radialen vs graden]] 