
---

type: concept  
category: physics

---

## Overzicht

**Ragdoll physics** simuleert een flexibel, ongecontroleerd lichaam dat reageert op krachten en botsingen, zoals een pop. Het is het tegenovergestelde van skeletal animation: in plaats van gekostumeerde beweging, volgt het lichaam natuurlijke physics.

## Kernidee

Ragdoll wordt bereikt door:

1. Het skelet op te delen in individuele kinematic rigidbodies (per bot/segment)
2. Deze met **joints** (Hinge, Fixed, Character) te verbinden
3. Op activering: alle rigidbodies op kinematic=false zetten → physics engine neemt over

## Gebruik in Unity

- **Death animations**: Karakter valt natuurlijk en interageert met omgeving
- **Knockback/impact**: Lichaam ragdolls bij grote impact
- **Procedural animation**: Fallback voor breuken/onmogelijke poses

## Veelvoorkomende patronen

- **Ragdoll activatie**: `rb.isKinematic = false` op alle botten wanneer nodig
- **Blending**: Animatie vs ragdoll smoother combineren
- **Constraints**: `rb.constraints` beperken onnatuurlijke bewegingen
- **Joint tuning**: Mass, drag, stiffness aanpassen per bot

## Code voorbeeld

csharp

```
// Ragdoll activeren wanneer karakter doodgaat 
public void ActivateRagdoll() 
{   
// Zet alle bones op dynamic    
Rigidbody[] rigidbodies = GetComponentsInChildren<Rigidbody>();    
foreach (Rigidbody rb in rigidbodies) 
{        rb.isKinematic = false;    }

// Voeg initiële kracht toe (optioneel)    
torsoRb.AddForce(Vector3.up * ragdollForce, ForceMode.Impulse); 
}
```

## Valkuilen / Best practices

- **Valkuil**: Ragdoll wordt gefrustreerd (jerky moves) → joints/colliders overlapping aanpassen
- **Valkuil**: Ragdoll valt door omgeving → collider grootte aanpassen
- **Best practice**: Beperk ragdoll beweging met `rb.constraints` (bijv. geen Y-rotatie voor bovenlichaam)
- **Best practice**: Test ragdoll setup in aparte scene zonder gameplay
- **Best practice**: Voeg kleine damping toe (Linear/Angular Damping) voor stabiliteit
- **Performance**: Ragdoll is duur (veel rigidbodies) → limit aantal active ragdolls

## Gerelateerde componenten

 [[Rigidbody]] - [[Joint]] - [[Collider]] 

## Gerelateerde functies

 [[Rigidbody.isKinematic (property)]] - [[Rigidbody.AddForce]]

## Gerelateerde concepten

 [[Kinematic vs dynamic rigidbodies]] - [[Torque en momentum]] - [[Center of mass]]