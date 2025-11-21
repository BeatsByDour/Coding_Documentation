Categorie: [[Unity/Category/Physics]]

Beschrijving:  
De Rigidbody is de basiscomponent voor fysiek gedrag op een GameObject in Unity; het maakt botsingen, zwaartekracht en krachten op objecten mogelijk.

## Properties
- [[Unity/Component/Rigidbody/mass]]
- [[Unity/Component/Rigidbody/drag]]
- [[Unity/Component/Rigidbody/velocity]]

## Methoden
- [[Unity/Component/Rigidbody/AddForce]]
- [[Unity/Component/Rigidbody/MovePosition]]
- [[Unity/Component/Rigidbody/AddTorque]]

## Gebruik
```
void Start() {  
Rigidbody rb = GetComponent<Rigidbody>();  
rb.mass = 2.0f;  
rb.AddForce(Vector3.up * 10.0f, ForceMode.Impulse);  
}
```

`## Zie ook 
- [[Unity/Component/BoxCollider]] 
- [[Unity/Type/ForceMode]]`