
---

type: concept  
category: physics

---

## Overzicht

**Torque** is rotatiekracht (moment), vergelijkbaar met hoe AddForce lineaire kracht is. **Momentum** is de traagheid van beweging (massa × velocity). Angular momentum is soortgelijk voor rotatie: traagheid × angular velocity.

## Kernidee

- **Torque (τ)**: Draaimomenten (Nm). Veroorzaakt rotatie, vergelijkbaar met F = m × a
- **Angular momentum (L)**: Het vermogen van een object om te blijven roteren (I × ω). Handig voor spineffecten
- **Inertia tensor**: Weerstand tegen rotatie, afhankelijk van vorm en massa-verdeling

Relatie: τ = I × α (Torque = Inertia × Angular acceleration)

## Gebruik in Unity

- **Visuele spin**: AddTorque voor draaiende effecten
- **Voertuigbesturing**: Yaw/Pitch/Roll via AddRelativeTorque
- **Balans-mechanica**: Angular damping aanpassen
- **Spinning projectiles**: Initiële spin geven

## Veelvoorkomende patronen

- **Continuous rotation**: `rb.angularVelocity = new Vector3(0, 5f, 0);`
- **Instant spin**: `rb.AddTorque(Vector3.up * 100f, ForceMode.Impulse);`
- **Flight controls**: `AddRelativeTorque` voor pitch/roll/yaw
- **Balance**: Angular damping verhogen voor minder spin

## Code voorbeeld

csharp

```
// Constant spin (niet via torque!) 
rb.angularVelocity = Vector3.up * spinSpeed; 

// Accelerating spin (via torque) 
rb.AddTorque(Vector3.up * torqueAmount); 

// Flight pitch control (lokaal) 
float pitch = Input.GetAxis("Vertical"); 
rb.AddRelativeTorque(Vector3.right * pitch * torqueAmount); 

// Check current spin 
float currentSpinSpeed = rb.angularVelocity.magnitude;
```

## Valkuilen / Best practices

- **Valkuil**: Velocity en AddForce combineren → conflicten
- **Valkuil**: Te hoog angular damping → object voelt zwaar/traag
- **Best practice**: Beperk angularVelocity magnitude met `maxAngularVelocity`
- **Best practice**: Zet `freezeRotation` op X/Z-assen voor platformers (geen accidentele tilts)
- **Best practice**: Test inertia tensor en constraints per object-type
- **Performance**: Veel spinning objects = veel berekeningen

## Gerelateerde componenten

- [[Rigidbody]] 

## Gerelateerde functies

 [[Rigidbody.AddTorque]] - [[Rigidbody.AddRelativeTorque]] - [[Rigidbody.angularVelocity (property)]]

## Gerelateerde concepten

[[Rotatie en koppel]] - [[Forces en beweging]] - [[Center of mass]] 