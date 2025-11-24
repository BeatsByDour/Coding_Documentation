
---

type: concept  
category: physics

---

## Overzicht

**Custom gravity** betekent het implementeren van eigen zwaartekracht-logica in plaats van Physics.gravity te gebruiken. Dit wordt gebruikt voor creatieve game designs: zwevende planeten, anti-gravity zones, of planeet-specifieke gravity (bijv. maan vs aarde).

## Kernidee

- **Standaard Physics.gravity**: Global, uniform (0, -9.81, 0)
- **Custom gravity**: Per object, locatie-afhankelijk, vector-afhankelijk
- **Implementatie**: Manual AddForce(), niet Physics.gravity gebruiken
- **Flexibiliteit**: Kan naar wil aangepast worden per game mechanic

## Gebruik in Unity

- **Multi-planet games**: Verschillende gravity per planeet
- **Gravity wells**: Attract object naar bepaald punt
- **Anti-gravity zones**: Opwaartse gravity in bepaalde regio's
- **Portal mechanics**: Gravity richting wijzigt bij portaal
- **3D platformers**: Zwaartekracht naar anders dan omlaag

## Veelvoorkomende patronen

- **Directional custom gravity**: Kracht in vaste richting (bijv. (0, -20, 0) voor harder vallen)
- **Point-based custom gravity**: Aantrekking naar bepaalde positie (zoals planeet)
- **Zone-based custom gravity**: Verschil gravity in bepaalde gebieden
- **Smoothly changing gravity**: Transitie tussen gravity richtingen

## Code voorbeeld

csharp

```
`// Eenvoudige custom gravity (sterker dan default) 
public float customGravity = -20f; 
void FixedUpdate() 
{     
rb.AddForce(Vector3.up * customGravity * rb.mass); 
} 

// Point-based gravity (planeet) 
Vector3 gravityDirection = (planetCenter - rb.position).normalized; 
float gravityStrength = 15f; 
rb.AddForce(gravityDirection * gravityStrength * rb.mass); 

// Zone-based gravity (switch op entering collider) 
public void EnterZeroGravityZone() {     rb.useGravity = false; } 
public void ExitZeroGravityZone() {     rb.useGravity = true; } 

// Smooth gravity transition 
Vector3 targetGravity = newPlanetGravity; rb.velocity += Vector3.Lerp(currentGravity, targetGravity, Time.fixedDeltaTime * transitionSpeed);`
```

## Valkuilen / Best practices

- **Valkuil**: Vergeten rb.useGravity = false zetten → double gravity effect
- **Valkuil**: Custom gravity als constant instellen → oncontroleerbaar
- **Best practice**: Definieer gravity constants per zone/object type
- **Best practice**: Visualiseer gravity richting in Gizmos (Scene view debugging)
- **Best practice**: Test gravity transitions op consoles (performance impact)
- **Best practice**: Beperk custom gravity bereik (Physics.OverlapSphere voor efficiency)
- **Performance**: Veel custom gravity objects = duur, use object pooling

## Gerelateerde componenten

 [[Rigidbody]] - [[Collider]] 

## Gerelateerde functies

[[Rigidbody.useGravity]] - [[Rigidbody.AddForce]] - [[Physics.gravity]] 

## Gerelateerde concepten

[[ Zwaartekracht en physics]] - [[ Forces en beweging]] - [[Physics update loop (FixedUpdate)]] 

---

