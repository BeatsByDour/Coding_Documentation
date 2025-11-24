
---

type: concept  
category: physics

---
## Overzicht

`FixedUpdate()` is een speciale Unity lifecycle-methode die wordt aangeroepen voor elke physics timestep, onafhankelijk van framerate. Dit is essentieel voor betrouwbare en consistente physics-simulatie.

## Kernidee

- **Update()**: Aangeroepen eenmaal per frame (variabel, afhankelijk van FPS)
- **FixedUpdate()**: Aangeroepen op vaste timestep (standaard 0.02s = 50 calls/sec), synchroon met physics engine

Physics berekeningen worden performed in vaste stappen. Alle physics-gerelateerde code (AddForce, MovePosition, Rigidbody aanpassingen) moet in FixedUpdate staan voor consistentie.

## Gebruik in Unity

- **Input lezen**: Update (snelle respons)
- **Beweging toepassen**: FixedUpdate (physics-stabiel)
- **Camera/animatie**: LateUpdate
- **Physics queries**: Kan in beide, maar FixedUpdate is voorkeur voor consistency

## Veelvoorkomende patronen

csharp

```
void Update() 
{     
// Input lezen   
 float inputX = Input.GetAxis("Horizontal");
} 
void FixedUpdate() {     
// Physics toepassen    
rb.AddForce(inputX * speed * transform.right); 
}
```

- **Fixed timestep instellen**: Edit > Project Settings > Time > Fixed Timestep
- **Multiple FixedUpdates per frame**: Als FPS > physics rate, gebeurt dit automatisch
- **Geen FixedUpdates per frame**: Als FPS < physics rate, worden frames overgeslagen

## Code voorbeeld

csharp

```
void Update() 
{
     // Lees input    
     moveDirection = Input.GetAxis("Vertical"); 
} 
void FixedUpdate() 
{     
	// Pas physics toe   
	 rb.AddForce(transform.forward * moveDirection * acceleration);         
	 // Verplaats kinematic rigidbody    
	 rb.MovePosition(rb.position + transform.forward * speed * Time.fixedDeltaTime); 
}
```

## Valkuilen / Best practices

- **Valkuil**: Physics code in Update i.p.v. FixedUpdate → jittery, onbetrouwbaar gedrag
- **Valkuil**: Time.deltaTime in FixedUpdate gebruiken (moet Time.fixedDeltaTime zijn)
- **Best practice**: Alle AddForce, MovePosition, velocity-wijzigingen in FixedUpdate
- **Best practice**: Input lezen in Update, toepassen in FixedUpdate
- **Performance**: Te laag FixedUpdate → physics voelt traag, te hoog → veel berekeningen

## Gerelateerde componenten

 [[Component/Rigidbody|Rigidbody]] 

## Gerelateerde functies

 [[Rigidbody.AddForce]] - [[Rigidbody.MovePosition]] 

## Gerelateerde concepten

[[Forces en beweging]] - [[Kinematic vs dynamic rigidbodies]] 