
---

type: unity-function  
component: Rigidbody  
category: physics

---

## Component / Namespace

- Component: Rigidbody
- Namespace: `UnityEngine`

## Beschrijving

Voegt een draaimoment toe in de lokale coördinatenruimte van het Rigidbody. Handig voor rotatie-controle relatief aan de huidige oriëntatie van het object, zoals roll/pitch/yaw voor voertuigen of vliegtuigen.

## Signatuur

csharp

```
void AddRelativeTorque(Vector3 torque, ForceMode mode = ForceMode.Force);
```

## Parameters

- **torque** – [[Vector3]] – Draaimoment in lokale ruimte (bijv. `Vector3.up` = yaw).
- **mode** – [[Forcemode]] (optioneel) – Bepaalt hoe het moment wordt toegepast (standaard `ForceMode.Force`).

## Retourwaarde

- Geen returnwaarde.

## Gedrag / Opmerkingen

- Aanroepen in `FixedUpdate`.
- Werkt alleen op niet-kinematic rigidbodies.
- Perfect voor flight controls of voertuig-stuurmechanismen.

## Voorbeeld

csharp

```
float pitch = Input.GetAxis("Vertical"); rb.AddRelativeTorque(Vector3.right * pitch * torqueAmount);
```

## Gerelateerde functies

 [[Rigidbody.AddTorque]] - [[Rigidbody.AddRelativeForce]] 

## Zie ook (concepten)

 [[Lokale vs wereldruimte]] - [[Rotatie en koppel]] 
