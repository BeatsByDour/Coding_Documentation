Date: 2025-03-24
Main: [[Movement]]
Sub: [[PlayerMovement]], [[Programming_Notes/Unity_00Overview/Rigidbody]]
Taal/editor: [[CSharp]],[[Unity]]
Desc: Dit script is geschreven om de speler te laten bewegen doormiddel van een rigidbody component op de speler.  Het gebruikte voorbeeld script heeft een dependecy aan de inputmanager script voor de gebruikte input van de speler te gebruiken voor de movement

voorbeeld code: 
`
    Rigidbody rb;

    Vector2 forwardInput;

    float x_Movement;
    float y_Movement;
    float z_Movement;
    [Range(1,50)]
    [SerializeField] float speed;

    void Start()
    {
        rb = GetComponent<Rigidbody>();
        Debug.Log(rb.gameObject.name);
    }

    // Update is called once per frame
    void Update()
    {
        CalcMovement();
        Vector3 moveDirection = (InputManager.instance.GetCamera().transform.right * x_Movement)  + (InputManager.instance.GetCamera().transform.forward * z_Movement);

        // Debug logs to check the calculated move direction
     //   Debug.Log("Move Direction: " + moveDirection);

        rb.MovePosition( rb.position + moveDirection * Time.deltaTime);
       //rb.MovePosition = transform.forward * Time.deltaTime * forwardInput * speed;
    }
    #region Functions

    private void CalcMovement()
    {
        x_Movement = InputManager.instance.movementInput.x * speed;
        z_Movement = InputManager.instance.movementInput.y * speed;

        // Debug logs to check x_Movement and z_Movement values
    //    Debug.Log("x_Movement: " + x_Movement + ", z_Movement: " + z_Movement);
    }
   `

In de code kan je zien dat je eerst een Rigidbody component gaat zoeken op de speler zelf en daarna plaats je deze op de rigidbody variabele. Deze heb je nodig om de rb.position functie te gebruiken. In deze functie wil je liefts de player inputs vermenigvuldigen met de [[Time.deltatime]] parameter.  Voordat je de rb.moveposition doet ga je eerst de X en Z as inputs berekenen. Dit heb ik gedaan door de functie calcMovement waar ik in deze variabelen de x en y inputs van de input vector2 vermenigvuldig met de speed variabele en plaats deze in de x_movement en y_movenent variabelen. Deze gebruik ik dan om de vector 3 movedirection te bereken. 
Movedirection vermenigvuldig je hierna met de time.deltatime in de rb.moveposition. 
