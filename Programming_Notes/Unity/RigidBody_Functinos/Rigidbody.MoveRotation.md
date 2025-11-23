
---

type: unity-function  
component: Rigidbody  
category: physics

---

## Component / Namespace

- Component: Rigidbody
    
- Namespace: `UnityEngine`
    

## Beschrijving

Roteert een kinematic Rigidbody naar een doelrotatie tijdens de volgende physics update, met behoud van collision-resolutie. Geschikt voor gecontroleerde rotaties zonder torque.

## Signatuur

csharp

`void MoveRotation(Quaternion rot);`

## Parameters

- **rot** – Quaternion – Doelrotatie in wereldruimte.
    

## Retourwaarde

- Geen returnwaarde.
    

## Gedrag / Opmerkingen

- Alleen voor kinematic rigidbodies.
    
- Overschrijft angularVelocity – niet combineren met AddTorque.
    
- Gebruik in `FixedUpdate`.
    

## Voorbeeld

csharp

`Quaternion targetRot = Quaternion.LookRotation(targetDirection); rb.MoveRotation(Quaternion.Slerp(rb.rotation, targetRot, Time.fixedDeltaTime * rotSpeed));`

## Gerelateerde functies

<!-- - [[Rigidbody.MovePosition]] - [[Rigidbody.AddTorque]] -->

## Zie ook (concepten)

<!-- - [[Concept – Kinematic vs dynamic rigidbodies]] - [[Concept – Quaternions]] -->