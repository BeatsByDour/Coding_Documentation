
---

type: concept  
category: physics

---

## Overzicht

Forces (krachten) zijn de basis van physics-gebaseerde beweging in Unity. In plaats van posities direct aan te passen, simuleer je realistische beweging door krachten toe te passen op Rigidbody-componenten.

## Kernidee

Newton's tweede wet: F = m × a (Kracht = massa × versnelling). Unity's physics engine berekent automatisch hoe objecten bewegen op basis van toegepaste krachten, massa, wrijving en zwaartekracht. Dit zorgt voor natuurlijk ogende beweging en automatische collision-resolutie.

## Gebruik in Unity

- **AddForce**: Continue kracht (zoals motor, wind)
- **ForceMode.Impulse**: Plotselinge kracht (explosie, sprong)
- **ForceMode.Acceleration**: Directe versnelling (negeer massa)
- **ForceMode.VelocityChange**: Directe snelheidswijziging

## Veelvoorkomende patronen

- **Character movement**: AddForce in FixedUpdate op basis van input
- **Vehicle physics**: Combinatie van forward thrust en turning torque
- **Projectiles**: Initial impulse bij spawning, daarna alleen gravity
- **Environmental effects**: Continue wind/water forces

## Code voorbeeld

csharp

```
void FixedUpdate() {     // Gradual acceleration (realistic)    float input = Input.GetAxis("Horizontal");    rb.AddForce(transform.right * input * acceleration);         // Instant jump (impulse)    if (Input.GetButtonDown("Jump")) {        rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse);    } 
}
```

## Valkuilen / Best practices

- **Valkuil**: Forces toepassen in Update i.p.v. FixedUpdate → inconsistente beweging
- **Valkuil**: AddForce combineren met directe Transform.position wijzigingen → conflicts
- **Best practice**: Kies tussen force-based (dynamic) OF position-based (kinematic) beweging
- **Best practice**: Gebruik passende ForceMode voor het gewenste effect

## Gerelateerde componenten

 [[Rigidbody]] - [[Collider]] 

## Gerelateerde functies

- [[Rigidbody.AddForce]] - [[Rigidbody.AddRelativeForce]] - [[Rigidbody.Velocity (property)]]

## Gerelateerde concepten

 [[Physics update loop (FixedUpdate)]] - [[Kinematic vs dynamic rigidbodies]] - [[Forcemode]] 

## Externe bronnen

- [Unity Manual – Physics](https://docs.unity3d.com/Manual/PhysicsSection.html)
    
- [Unity Learn – Physics](https://learn.unity.com/tutorial/physics)