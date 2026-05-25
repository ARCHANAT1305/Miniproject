# Ex.No: 10  Implementation of 2D/3D game 
### DATE: 25/5/26                                                                           
### REGISTER NUMBER : 212223240013
### AIM: 
To develop a Gravity Flip Escape 2D game using Unity.
### Algorithm:
```
1. Create a 2D project in Unity.
2. Add player, ground, ceiling, and obstacles.
3. Attach Rigidbody2D and Collider components.
4. Create player movement script using C#.
5. Implement left and right movement using keyboard input.
6. Implement jumping using Space key.
7. Implement gravity flip using G key.
8. Detect collisions with ground and obstacles.
9. Restart the game when player touches obstacles.
10. Complete the level when player reaches exit door.
```  
### Program:
```
using UnityEngine;

public class PlayerMovement : MonoBehaviour
{
    private Rigidbody2D rb;

    void Start()
    {
        rb = GetComponent<Rigidbody2D>();
    }

    void Update()
    {
        float move = Input.GetAxis("Horizontal");

        rb.velocity = new Vector2(move * 5f, rb.velocity.y);

        // JUMP
        if (Input.GetKeyDown(KeyCode.Space))
        {
            rb.velocity = new Vector2(rb.velocity.x, 10f);
        }

        // GRAVITY FLIP
        if (Input.GetKeyDown(KeyCode.G))
        {
            if (rb.gravityScale > 0)
            {
                rb.gravityScale = -3;
            }
            else
            {
                rb.gravityScale = 3;
            }

            transform.Rotate(0f, 0f, 180f);
        }
    }
}
```
### Output:
<img width="678" height="382" alt="image" src="https://github.com/user-attachments/assets/d3d98541-853d-49a5-81da-8119cb4dce82" />
<img width="547" height="383" alt="image" src="https://github.com/user-attachments/assets/90d6a8ad-9134-48ac-9b44-1f56c70bd6ca" />
<img width="533" height="385" alt="image" src="https://github.com/user-attachments/assets/cfe28fc3-e97e-489a-8257-74153976cec7" />


### Result:
Thus the Gravity Flip Escape 2D game was developed successfully using Unity and adopted basic game AI and physics technology.
