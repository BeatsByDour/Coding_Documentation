
---

type: concept  
category: physics

---

## Overzicht

**Zwaartekracht** is een globale force die alle dynamic rigidbodies naar beneden trekt. In Unity wordt dit ingesteld via `Physics.gravity` en kan per rigidbody worden toggled met `rb.useGravity`. Dit is essentieel voor platformers, fallende objecten en realistische beweging.

## Kernidee

- **Physics.gravity**: Global gravitational force (standaard ~9.81 m/s² downward = Vector3(0, -9.81, 0))
- **useGravity**: Boolean per rigidbody om zwaartekracht in/uit te schakelen
- **Scale matters**: Unitaire schaal is 1 meter; objecten lijken traag te vallen als ze 100× te groot zijn
- **Mass effect**: Zwaartekracht beïnvloedt alle massa's even veel (F = m × g, maar a = g is hetzelfde)

## Gebruik in Unity

- **Platformers**: Zwaartekracht aan, maar begrenzen valsnelheid
- **Flying objects**: `useGravity = false` voor vliegtuigen, UFO's
- **Zero-gravity zones**: Custom gravity in bepaalde gebieden
- **Scale tuning**: Aanpassen Physics.gravity voor game feel (sneller/langzamer vallen)

## Veelvoorkomende patronen

- **Jump mechanic**: Jump force > gravity effect
- **Terminal velocity**: Voeg air resistance/damping toe
- **Floating objects**: `useGravity = false`
- **Slow-motion**: Verlaag Physics.gravity en andere krachten

## Code voorbeeld

csharp

```
	// Standaard zwaartekracht uitlezen 
Vector3 currentGravity = Physics.gravity; // Meestal (0, -9.81, 0) 

	// Zwaartekracht voor dit rigidbody uitzetten (zweven) 
rb.useGravity = false; 
	// Custom zwaartekracht per rigidbody toepassen 
rb.useGravity = false; 
rb.AddForce(Physics.gravity * rb.mass); // Zelfde als standaard 
	// Zwaartekracht begrenzen met terminal 
velocity float fallVelocity = rb.velocity.y; 
if (fallVelocity < -maxFallSpeed) 
{     
rb.velocity = new Vector3(rb.velocity.x, -maxFallSpeed, rb.velocity.z); 
} 
// Scene gravity aanpassen voor game feel 
Physics.gravity = new Vector3(0, -15f, 0); // Sneller vallen
```

## Valkuilen / Best practices

- **Valkuil**: Objecten 100× te groot → vallen lijkt traag (fix: schaal normaliseren)
- **Valkuil**: useGravity = false vergeten voor flying objects → onwerkbaar gedrag
- **Best practice**: Zwaartekracht globaal consistent houden, niet per object varieren
- **Best practice**: Voeg damping toe (linearDamping) voor air resistance
- **Best practice**: Test jump height door `jumpForce = jumpHeight * Physics.gravity.magnitude`
- **Performance**: Physics.gravity wijzigen beïnvloedt hele engine (avoid in FixedUpdate loop)

## Gerelateerde componenten

 [[Component/Rigidbody]] 

## Gerelateerde functies

[[Rigidbody.useGravity]] - [[Physics.gravity]] - [[Rigidbody.AddForce]] 

## Gerelateerde concepten

[[ Forces en beweging]] - [[ Physics update loop (FixedUpdate)]] - [[ Snelheid en versnelling]] 