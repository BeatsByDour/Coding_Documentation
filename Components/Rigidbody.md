Categorie: [[Physics]]

Beschrijving:  
De Rigidbody is de basiscomponent voor fysiek gedrag op een GameObject in Unity; het maakt botsingen, zwaartekracht en krachten op objecten mogelijk.

## Properties
[[Rigidbody.Velocity (property)]]
[[Rigidbody.useGravity (property)]]
[[Rigidbody.isKinematic (property)]]
[[Rigidbody.angularVelocity (property)]]
[[Rigidbody.mass (property)]]
[[Rigidbody.maxAngularVelocity (property)]]

## Methoden
[[Rigidbody.MoveRotation]]
[[Rigidbody.Addforce]]
[[Rigidbody.AddTorque]]
[[Rigidbody.MovePosition]]
[[Rigidbody.AddRelativeForce]]
[[Rigidbody.AddRelativeTorque]]
[[Rigidbody.AddExplosionForce]]
[[Rigidbody.AddForceAtPosition]]


## Gebruik
```
void Start() {  
Rigidbody rb = GetComponent<Rigidbody>();  
rb.mass = 2.0f;  
rb.AddForce(Vector3.up * 10.0f, ForceMode.Impulse);  
}
```

`## Zie ook 
- [[BoxCollider]] 
- [[ForceMode]]