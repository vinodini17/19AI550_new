# Ex.No: 10  Implementation of 2D/3D game called Hurdle Game - 2D
### DATE: 20.05.2025                                                                       
### REGISTER NUMBER : 212223040244
### AIM: 
To develop a game using C# program in Unity 
### Algorithm:

Step 1: Create a new project.

Step 2: Click Content browser -> Drag the file into Unity -> Place the assets inside the viewport in Unity.

Step 3: Define the physics properties of the objects such as the collider.

Step 4: Assets -> Create -> # Script.

Step 5: Create a Coding folder and create a C# file to add the coding.

Step 6: To add our C# Script file to our selected object, click on the C# Script file drag it to our selected objects in the Hierarchy window and run the application.

Step 7: Stop.

### Program:
### Player.cs
```
using System.Collections;
using System.Collections.Generic;
using System.Security.Cryptography;
using UnityEngine;
using UnityEngine.SocialPlatforms.Impl;

public class player : MonoBehaviour
{
    public float speed;
    public float jumpforce;
    private Rigidbody2D rb;
    public Score cc;
    // Start is called before the first frame update
    void Start()
    {
        rb = GetComponent<Rigidbody2D>();
    }

    // Update is called once per frame
    void Update()
    {
        float moveinp = Input.GetAxisRaw("Horizontal");
        transform.position += new Vector3(moveinp, 0, 0) * speed * Time.deltaTime;
        if (Input.GetKeyDown(KeyCode.Space) &&Mathf.Abs(rb.velocity.y) < 0.001f)
        {
            rb.AddForce(new Vector2(0, jumpforce), ForceMode2D.Impulse);
        }
    }
    private void OnTriggerEnter2D(Collider2D other)
    { 
        if(other.CompareTag("Destroy"))
        {
            //cc.coincount++;
            Destroy(other.gameObject);
        }
    }
}

```
### Score.cs
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;
public class Score : MonoBehaviour
{
    public int coincount;
    public Text value;
    // Start is called before the first frame update
    void Start()
    {

    }

    // Update is called once per frame
    void Update()
    {
        value.text = coincount.ToString();
    }
}
```
### Output:
![431733157-17109be2-ca10-486c-8eb3-1604225a9f6a](https://github.com/user-attachments/assets/fcdee61e-3f84-43a9-ba24-766813fef5d0)

![431733224-f95418d2-bf9f-49f2-b021-e17fe5fe4e53](https://github.com/user-attachments/assets/b46dc113-4a81-417e-be6f-98f02518916e)

### Result:
Thus a 2D game using the C# program in Unity is developed successfully.
