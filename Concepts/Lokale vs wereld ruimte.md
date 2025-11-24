
---

type: concept  
category: physics

---

## Overzicht

**Wereld ruimte** is de globale coördinaatsysteem van de scene. **Lokale ruimte** is relatief aan elk object (vooruit, rechts, omhoog vanuit het perspectief van dat object). Veel functies hebben twee versies: `AddForce` (wereld) vs `AddRelativeForce` (lokaal).

## Kernidee

- **Wereld ruimte**: (0,0,1) = naar camera, (1,0,0) = rechts, (0,1,0) = omhoog → onafhankelijk van object rotatie
- **Lokale ruimte**: (0,0,1) = vooruit object, (1,0,0) = rechts object, (0,1,0) = omhoog object → relatief aan rotatie

Conversie: `localVector = transform.TransformDirection(worldVector)`

## Gebruik in Unity

- **Character movement**: Local (vooruit = waar karakter naar kijkt)
- **Physics queries**: World (collision checks in scene-coördinaten)
- **Vehicle controls**: Local (stuur relatief aan voertuigrichting)
- **Explosies**: World (kracht van externe bron)

## Veelvoorkomende patronen

- **Player forward thrust**: `AddRelativeForce(Vector3.forward)` → beweegt in zijkant
- **Turning**: `AddRelativeTorque(Vector3.up)` → yaw relatief aan object
- **Knockback**: `AddForce(direction)` → wereld-richting
- **Coordinate conversion**: `transform.TransformPoint()`, `InverseTransformPoint()`

## Code voorbeeld

csharp

```
// Lokale beweging (vooruit = waar het object naar kijkt) 
void FixedUpdate() 
{     
rb.AddRelativeForce(Vector3.forward * acceleration);
} 

// Wereld beweging (vooruit = wereldas Z) 
void FixedUpdate() 
{     
rb.AddForce(Vector3.forward * acceleration); 
} 

// Conversie 
Vector3 worldForward = transform.TransformDirection(Vector3.forward); 
Vector3 localForward = transform.InverseTransformDirection(Vector3.forward);
```

## Valkuilen / Best practices

- **Valkuil**: AddRelativeForce gebruiken voor explosies → rare resultaten
- **Valkuil**: Verwarring tussen TransformDirection en TransformPoint
- **Best practice**: Local voor object-centric controls (player, vehicle)
- **Best practice**: World voor externe events (explosies, wind, knockback)
- **Best practice**: Always check documententatie voor coördinaatsysteem
- **Debugging**: Gizmo's in lokale vs wereldruimte visualiseren

## Gerelateerde componenten

 [[Rigidbody]] - [[Transform]] 

## Gerelateerde functies

[[Rigidbody.AddRelativeForce]] - [[Rigidbody.AddForce]] - [[Transform.TransformDirection]] 

## Gerelateerde concepten

[[Forces en beweging]] - [[Rotatie en koppel]] 