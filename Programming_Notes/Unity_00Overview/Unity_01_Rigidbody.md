Date: 2025-03-24
Main: [[parsing]]
Sub: [[class parsing]]
Taal/editor: [[CSharp]],[[Unity]]
Desc: Class parsing heb ik gebruikt in mijn unity code om een json script te parsen in csharp code. de csharp code wordt daarna omgezet naar een class die ik daarna kan gebruiken als bijvoorbeeld een abilty class waar dmg,cooldown,naam,id en description in zit.

Deze code heeft wel een dependency aan de jsonconverter package 

Een voorbeeld van de JSON code:

```
[
  {
    "id": 200,
    "name": "Static",
    "desc": "Your abilities create a static that phazes through other enemies ",
    "unlocked": "true",
    "functionName": "CastStatic",
    "counter": 0,
    "cooldown": 5
  },
  {
    "id": 201,
    "name": "Ice",
    "desc": "Your abilities slow the enemies",
    "unlocked": "true",
    "functionName": "CastIce",
    "counter": 0,
    "cooldown": 3
  },
  {
    "id": 202,
    "name": "Blaze",
    "desc": "Your attacks burn the enemies",
    "unlocked": "false",
    "functionName": "CastBlaze",
    "counter": 0,
    "cooldown": 6
  },
  {
    "id": 203,
    "name": "Ka-A-boom",
    "desc": "your attacks explode the enemies creating aoe damage",
    "unlocked": "false",
    "functionName": "CastKaABoom",
    "counter": 0,
    "cooldown": 5
  },
  {
    "id": 204,
    "name": "Magnetize",
    "desc": "The enemy you hit pulls in other enemies",
    "unlocked": "false",
    "functionName": "CastMagnetize",
    "counter": 0,
    "cooldown": 2
  },
  {
    "id": 205,
    "name": "Boulder",
    "desc": "the enemy hit by the player will be knocked up in the air",
    "unlocked": "false",
    "functionName": "CastBoulder",
    "counter": 0,
    "cooldown": 7
  }
] 
```

Dit json script bevat verschillende variabelen die hieruit geparsed worden en in het onderstaande script worden gelezen en geplaatst inde ability class

Een voorbeeld van de interegratie in Unity c#:
```
using JetBrains.Annotations;
using System;
using System.Collections;
using System.Collections.Generic;
using System.Linq;
using UnityEditor;
using UnityEngine;


[Serializable]
public class AllAbilities : MonoBehaviour
{

    [SerializeField] string Filename;
    [SerializeField] bool useEncryption;
    [SerializeField] string Data2;
    [SerializeField] Ability Data;

 
    private List<Ability> playerAbilities = new List<Ability>();

    private FileDataHandler _dataHandler;

    private Dictionary<int, Action<Transform>> abilityActions;

    public static AllAbilities Instance;




    [Header("static")]
    [SerializeField] private Static_Ability staticObject;

    [Header("Blaze")]
    [SerializeField] private Blaze_Ability blazeAbility;

    [Header("KaAboom")]
    [SerializeField] private KaABoom_OAbility kaABoomObject;

    [Header("Magnetic")]
    [SerializeField] private Magnetic_Ability magneticAbility;

    [Header("Ice")]
    [SerializeField] private Ice_Ability IceObject;

    [Header("Boulder")]
    [SerializeField] private Boulder_Ability boulderAbility;

    private void Awake()
    {
        if (Instance != null)
        {
            Debug.Log(" there is already an allabiliets script active in this scene");
        }
        Instance = this;

        _dataHandler = new FileDataHandler(Application.persistentDataPath, Filename, useEncryption);
        LoadInAllAbilities();
        InitializeAbilityActions();
    }

    private void Start()
    {

       
    }

    // Initialize the dictionary that maps IDs to actual functions
    private void InitializeAbilityActions()
    {
        abilityActions = new Dictionary<int, Action<Transform>>
        {
            {  playerAbilities[0].id, CastStatic},
            {  playerAbilities[1].id, CastIce },
            {  playerAbilities[2].id, CastBlaze },
            {  playerAbilities[3].id, CastKaABoom },
            {  playerAbilities[4].id, CastMagnetize },
            {  playerAbilities[5].id, CastBoulder }
        };
    }

    // Use ability by ID if it's unlocked
    public void UseAbility(int id,Transform target)
    {
        Ability ability = playerAbilities.Find(a => a.id == id);
        if (ability != null && ability.unlocked)
        {
            if (abilityActions.TryGetValue(id, out var action))
            {
                action.Invoke(target);
            }
            else
            {
                Debug.LogWarning($"No action mapped for ability ID {id}.");
            }
        }
        else
        {
            Debug.Log($"{ability?.name ?? "Ability"} is locked or not found.");
        }
    }

    private void LoadInAllAbilities()
    {
        playerAbilities = _dataHandler.LoadAllAbilities();
        foreach (Ability ability in playerAbilities)
        {

            Data2 += ability.unlocked + ", ";

            if (ability.unlocked)
            {

            }

        }
        Debug.Log(Data2);

    }

    private void Update()
    {
        if (Input.GetKeyDown(KeyCode.L)) 
        {
            LoadInAllAbilities();
            Debug.Log("Test Load");
        }
    }

    private void CastStatic( Transform targethit)
    {
        Debug.Log("CastStatic");

        staticObject.ShootTarget(targethit);

    }
    private void CastIce(Transform targethit)
    {
       Debug.Log("CastIce");
       IceObject.StartFreeze(targethit);
    }   
    private void CastBlaze( Transform transform)
    {
          Debug.Log("CastBlaze");
        blazeAbility.StartBlaze(transform);
    }   
    private void CastKaABoom( Transform transform)
    {
        Debug.Log("CastKaABoom");
        kaABoomObject.CastExplosion(transform);
    }   
    private void CastMagnetize( Transform transform)
    {
          Debug.Log("CastMagnetize");
    }   
    private void CastBoulder( Transform transform)
    {
          Debug.Log("CastBoulder");
        boulderAbility.StartBoulder(transform);
    }

    public List<Ability> GetPlayerAbilities()
    {
        return playerAbilities;
    }

}

public class Ability
{
    public int id;
    public  string name;
    public string desc;
    public bool unlocked;
    public string functionName;
    public int counter;
    public int cooldown;
  


    //public Ability(int id, string name, string description,bool unlocked)
    //{
    //    this.id = id;
    //    this.name = name;
    //    this.desc = description;
    //    this.unlocked =  unlocked;
        

    //}

    public void Unlock()
    {
        unlocked = true;
        UnityEngine.Debug.Log($"{name} has been unlocked!");

    }

    public void setCounter(int count)
    {
        counter = count;
    }
  

}

``````

Deze code leest het json script in en plaatst deze in de ability class. Hierna wordt deze class geplaatst in een dictionary om zo van elkaar te kunnen onderschrijden en de verschillende functies eraan te linken.

Deze code kan ook gebruikt worden in andere opzichten zoals als safe file. Als dit als safe file gebruikt moet worden moet dit wel mogelijk ge encrypt worden en kan beter niet opgeslagen worden op de speler zijn computer maar op een cloud.

voor de rest is dit een makkelijke manier om grote lijsten van items,spells,enemys of stat blokken om te zetten in game code.