 
---

type: unity-function  
component: [[Rigidbody]]  
category: [[Physics]]

---

## Component / Namespace

- Component: [[Rigidbody]]
    
- Namespace: `UnityEngine`
    

## Beschrijving

Simuleert een explosiekracht die objecten wegduwt vanuit een centraal punt. De kracht neemt af met afstand en kan een upward modifier krijgen voor realistische explosie-effecten.

## Signatuur

csharp

```
void AddExplosionForce(float explosionForce, Vector3 explosionPosition, float explosionRadius, float upwardsModifier = 0.0f, ForceMode mode = ForceMode.Force);
```

## Parameters

- **explosionForce** – [[Float]] – Sterkte van de explosie.
- **explosionPosition** – [[Vector3]] – Centrum van de explosie in wereldruimte.
- **explosionRadius** – [[Float]] – Maximale afstand waarop de explosie effect heeft.
- **upwardsModifier** – [[Float]] (optioneel) – Extra opwaartse kracht voor realisme (standaard 0).
- **mode** – [[ForceMode]] (optioneel) – Hoe de kracht wordt toegepast (standaard `ForceMode.Force`).
## Retourwaarde

- Geen returnwaarde.

## Gedrag / Opmerkingen

- Kracht neemt lineair af met afstand tot explosionRadius.
- Gebruik `ForceMode.Impulse` voor directe explosie-impact.
- Werkt alleen op niet-kinematic rigidbodies binnen radius.

## Voorbeeld

csharp

```
rb.AddExplosionForce(500f, explosionPos, 10f, 3f, ForceMode.Impulse);
```

## Gerelateerde functies

 [[Rigidbody.AddForce]] - [[Rigidbody.AddForceAtPosition]] 

## Zie ook (concepten)

 [[Explosie effecten]] - [[Forcemode]] 