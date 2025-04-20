# Raycast 101

  Raycast is very popular among developers. In short, a raycast is like a basic laser/ray. There are many reasons for its usage, such as selecting the object that collides with your raycast.
  
  Note: In this tutorial, values or objects will be connected each other.
  ## Basic Ray:
  ```C#
  Vector3 origin = new Vector3(0,0,0);
  Vector3 direction = new Vector3(0,0,0);

  origin = transform.position;
  direction = transform.forward;

  Ray raycast1 = new Ray(origin, direction);
  ```
  - This code creates a basic ray.

  ## Debug.DrawRay():
  ```C#
  Color color = new Color(255, 255, 255);
  float duration = 10f;

  Debug.DrawRay(origin, direction, color, duration);
  ```
  - This ray is only visible in studio, not in game. 
    
  ## Hit Info:
  ```C#
  RaycastHit hitInfo;

  bool hit = Physics.Raycast(raycast1, out hitInfo);

  if(hit){
  //Get info from raycast
  Collider hitCollider = hitInfo.collider;
  Gameobject hitObject = hitInfo.collider.gameObject;
  }
  ```
  ## Physics.Linecast():
  ```C#
  Vector3 startPosition = new Vector3(0, 0, 0);
  Vector3 endPosition = new Vector3(1, 1, 1);

  RaycastHit hitInfo2;

  bool hit2 = Physics.Linecast(startPosition, endPosition, out hitInfo2);
  ```
  - This code creates a ray between 2 point (startPosition and endPosition).
  
