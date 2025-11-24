
---

type: concept  
category: physics

---

## Overzicht

**Snelheid (velocity)** is de snelheid waarmee een object van plaats verandert. **Versnelling (acceleration)** is de verandering van snelheid over tijd. In Unity zijn beide centraal voor natuurlijke beweging.

## Kernidee

- **Snelheid**: Vector die positieverandering per seconde aangeeft (m/s). Direct leesbaar via `rb.velocity`.
- **Versnelling**: Hoe snel snelheid verandert (m/s²). Bereikt via krachten (`AddForce` met `ForceMode.Acceleration`) of snelheidsmultiplicatie.

Relatie: F = m × a (Kracht = massa × versnelling)

## Gebruik in Unity

- **Lezen van velocity**: Controleer hoe snel een object beweegt (voor animaties, geluid, effecten)
- **Snelheid aanpassen**: Directe `velocity` wijziging voor instant effects (jump, knockback)
- **Versnelling via krachten**: AddForce voor geleidelijke, natuurlijke beweging

## Veelvoorkomende patronen

- **Jump**: Directe Y-velocity wijziging
- **Knockback**: Snelle velocity aanpassing bij impact
- **Smooth acceleration**: AddForce in FixedUpdate resulteert in geleidelijke velocity toename
- **Speed capping**: `rb.velocity = Vector3.ClampMagnitude(rb.velocity, maxSpeed)`

## Code voorbeeld

csharp

```
// Snelheid uitlezen 
float currentSpeed = rb.velocity.magnitude; 

// Direct snelheid aanpassen (instant jump) 
Vector3 vel = rb.velocity; vel.y = jumpSpeed; rb.velocity = vel;
 
// Versnelling via AddForce (geleidelijk) 
void FixedUpdate() {   
rb.AddForce(transform.forward * acceleration, ForceMode.Acceleration); } 

//Snelheid begrenzen 
if (rb.velocity.magnitude > maxSpeed) 
	{ rb.velocity = rb.velocity.normalized * maxSpeed; }


```

## Valkuilen / Best practices

- **Valkuil**: Snelheid direct wijzigen in Update i.p.v. FixedUpdate → inconsistent
- **Valkuil**: AddForce en directe velocity wijzigingen op dezelfde frame → onverwacht gedrag
- **Best practice**: Directe velocity wijzigingen voor instant effects, AddForce voor geleidelijke beweging
- **Best practice**: Gebruik `velocity.magnitude` voor snelheidscontrole, niet alleen X/Z
- **Performance**: Cache `rb.velocity` als je het meerdere keren nodig hebt

## Gerelateerde componenten

[[Rigidbody]]

## Gerelateerde functies

[[Rigidbody.Velocity (property)]] - [[Rigidbody.AddForce]] 

## Gerelateerde concepten

 [[Forces en beweging]] - [[Physics update loop (FixedUpdate)]]

