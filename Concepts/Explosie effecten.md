

---

type: concept  
category: physics

---

## Overzicht

**Explosie effecten** simuleren krachten die vanuit een centraal punt alle nabije objecten wegduwen. Dit wordt bereikt via `AddExplosionForce()`, die automatisch afstandsberekening, falloff en opwaartse boost handelt.

## Kernidee

Explosies hebben:

- **Epicentrum**: Centraal punt van explosie
- **Radius**: Maximale affectafstand
- **Falloff**: Kracht neemt lineair af met afstand
- **Upward modifier**: Extra opwaartse component voor realistisch effect (objecten vliegen omhoog)

## Gebruik in Unity

- **Granaten/bomben**: Ontploffen en werpen objecten weg
- **Mijn-explosies**: Gebied-schade met physics
- **Environmental hazards**: Lavakraters, luchtvortices
- **Game event effects**: Earthquake, shockwave simulatie

## Veelvoorkomende patronen

- **Point explosion**: Eenmalige explosie op locatie
- **Area damage**: Explosie + health reduction
- **Debris**: Spawning van flying objects na explosie
- **Camera shake**: Sync explosie met camera effect

## Code voorbeeld

csharp

```
// Explosie toepassen op alle nearby rigidbodies 
public void CreateExplosion(Vector3 position, float force, float radius) 
{     
Collider[] colliders = Physics.OverlapSphere(position, radius);         
foreach (Collider col in colliders) 
{        
Rigidbody rb = col.GetComponent<Rigidbody>();        
if (rb != null)
{            // force=500, radius=10, upwardMod=3            rb.AddExplosionForce(force, position, radius, 3f, ForceMode.Impulse);        }    }        
 // Visueel effect    
Instantiate(explosionEffect, position, Quaternion.identity); }
```

## Valkuilen / Best practices

- **Valkuil**: ForceMode.Force gebruiken i.p.v. Impulse → zwak, voelt traag
- **Valkuil**: Radius te klein → niet alle objecten worden getroffen
- **Best practice**: `ForceMode.Impulse` voor snelle explosie-effecten
- **Best practice**: Testexplosie-radius visueel met Gizmos in Scene view
- **Best practice**: Voeg damping toe aan getroffen objecten (friction, air resistance)
- **Optimization**: Use Physics.OverlapSphere met layer mask filter

## Gerelateerde componenten

[[Rigidbody]] - [[Collider]] 

## Gerelateerde functies

[[Rigidbody.AddExplosionForce]] - [[Physics.OverlapSphere]] 

## Gerelateerde concepten

[[Forces en beweging]] - [[Physics update loop (FixedUpdate)]]