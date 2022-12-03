//this ulas's first game's code

using System.Collections;
using System.Collections.Generic;
using UnityEngine;
/* public class "   " : MonoBehaviour тырнақшаға өзін ашқан script-тің атың жазасын */
public class PlayerContoller : MonoBehaviour
{
  
    public float speed = 3f;
    public float jumpForce = 3f;
    private float moveInput;
    
    private Rigidbody2D rb;
   
    private bool isGrounded;
    public Transform groundCheck;
    public float checkRadius;
    public LayerMask whatIsGround;
    
   
    
    private int extraJumps;
    public int extraJumpsValue;
   
    private void Start()
    {
       extraJumps = extraJumpsValue;
        rb=GetComponent<Rigidbody2D>();
    }
 
    private void FixedUpdate()
    {
        isGrounded = Physics2D.OverlapCircle(groundCheck.position, checkRadius, whatIsGround);
        
        //
        float moveInput = Input.GetAxisRaw("Horizontal");
        rb.velocity = new Vector2 (moveInput * speed, rb.velocity.y);
        //бұл код арқылы горизанталь бойынша жүруге болады 
        
    }
     private void Update()
    {
        //
        if(isGrounded == true )
        {
            extraJumps = extraJumpsValue;
        }
        
        if(Input.GetKeyDown(KeyCode.UpArrow) && extraJumps >0) 
        {
            rb.velocity = Vector2.up * jumpForce;
            extraJumps--;
        }if(Input.GetKeyDown(KeyCode.UpArrow) && extraJumps == 0 && isGrounded == true )
        {
            rb.velocity = Vector2.up * jumpForce;
        }
       
    }
}
