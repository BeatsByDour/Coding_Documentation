
---

type: unity-property  
component: [[Rigidbody]]  
category: [[Physics]]

---

## Component / Namespace

- Component: [[Rigidbody]]
- Namespace: `UnityEngine`

## Beschrijving

Bepaalt of het Rigidbody wordt beïnvloed door de globale zwaartekracht (Physics.gravity). Handig voor objecten die zweven of eigen zwaartekracht-logica hebben.

## Signatuur

csharp

```
bool useGravity { get; set; }
```

## Parameters

- Geen (is een property).

## Retourwaarde

- [[Bool]] – `true` = zwaartekracht aan, `false` = uit.

## Gedrag / Opmerkingen

- Standaard is `true` voor dynamic rigidbodies.
- Uitzetten voor vliegende objecten, ruimteschepen, of zwevende platforms.
- Heeft geen effect op kinematic rigidbodies.

## Voorbeeld

csharp

```
// Zwaartekracht uitzetten voor zwevend object rb.useGravity = false;
```

## Gerelateerde functies

 [[Physics.gravity]] - [[Rigidbody.AddForce]] 

## Zie ook (concepten)

 [[Zwaartekracht en physics]] - [[Custom gravity]] 