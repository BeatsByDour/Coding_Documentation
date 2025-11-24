
---

type: concept  
category: physics

---
## Overzicht

Kinematic en dynamic rigidbodies zijn twee verschillende manieren waarop Unity Rigidbody-objecten kan simuleren. Dynamic rigidbodies worden gecontroleerd door de physics engine (krachten, zwaartekracht), terwijl kinematic rigidbodies volledig door scripts of animaties worden bestuurd.

## Kernidee

- **Dynamic**: Physics engine bepaalt beweging. Objecten reageren op krachten, zwaartekracht en botsingen.
- **Kinematic**: Scripts bepalen beweging via `MovePosition()` en `MoveRotation()`. Physics engine handelt alleen collisions af.

Kinematic rigidbodies worden niet beïnvloed door AddForce of zwaartekracht, maar kunnen wel botsingen veroorzaken en detecteren.

## Gebruik in Unity

- **Dynamic**: Fysieke objecten (ballen, voertuigen, ragdolls, projectiles)
- **Kinematic**: Platforms, deuren, player controller (zonder physics), bewegende obstakels, animatie-gecontroleerde objecten

## Veelvoorkomende patronen

- **Smooth player movement**: Kinematic rigidbody met MovePosition()
- **Ragdoll activatie**: Switch van kinematic naar dynamic on-demand
- **Moving platforms**: Kinematic parent met dynamic children
- **Physics-based vehicles**: Dynamic rigidbody met AddForce/AddTorque

## Code voorbeeld

csharp

```
// Switch van kinematic naar dynamic (ragdoll activatie) rb.isKinematic = false; // Kinematic movement (player controller) void FixedUpdate() {     Vector3 input = new Vector3(Input.GetAxis("Horizontal"), 0, Input.GetAxis("Vertical"));    rb.MovePosition(rb.position + input * speed * Time.fixedDeltaTime); } // Dynamic movement (AddForce) void FixedUpdate() {     rb.AddForce(Vector3.forward * acceleration); }
```

## Valkuilen / Best practices

- **Valkuil**: Kinematic en dynamic properties op hetzelfde frame wijzigen → onverwacht gedrag
- **Valkuil**: MovePosition combineren met AddForce → conflicterende beweging
- **Best practice**: Kies één aanpak: óf force-based (dynamic) óf position-based (kinematic)
- **Best practice**: Gebruik kinematic voor speelbare karakters, dynamic voor interactieve objecten
- **Performance**: Kinematic rigidbodies zijn lichter dan dynamic (minder berekeningen)
    

## Gerelateerde componenten

 [[Rigidbody]] - [[Collider]]

## Gerelateerde functies

 [[Rigidbody.isKinematic (property)]] - [[Rigidbody.MovePosition]] - [[Rigidbody.AddForce]] 

## Gerelateerde concepten

 [[Forces en beweging]] - [[Physics update loop (FixedUpdate)]] - [[Ragdoll physics]] 