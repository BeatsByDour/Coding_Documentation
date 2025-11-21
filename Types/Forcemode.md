# ForceMode

Beschrijving:  
`ForceMode` is een enum die bepaalt hoe een kracht door AddForce, AddTorque of aanverwante functies op een Rigidbody wordt toegepast.

## Syntax
`enum ForceMode { Force, Acceleration, Impulse, VelocityChange }`

## Waarden
- `Force`: Toepassing van een continue kracht (standaard).
- `Acceleration`: Directe versnelling, zonder rekening met massa.
- `Impulse`: Plotselinge kracht, beïnvloed door massa.
- `VelocityChange`: Onmiddellijke snelheidsverandering zonder massa.

## Gebruik
```
rb.AddForce(Vector3.forward * 10.0f, ForceMode.Impulse);
```
## Zie ook 
- [[Unity/Component/Rigidbody]]
- [[Unity/Type/Vector3]]