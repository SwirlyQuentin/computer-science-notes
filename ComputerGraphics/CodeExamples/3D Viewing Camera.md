- Class to hold camera's position in 3D space

**Vector3Float** class
```java
public class Vector3Float{
	public float x, y, z;
	public Vector3Float(int x, int y, int z){
	this.x = x;
	this.y = y;
	this.z = z;
	}
}
```

First Person Camera Controller Class
```java
import org.lwjgl.util.vector.Vector3f;
import org.lwjgl.input.Keyboard;
import org.lwjgl.input.Mouse;
import org.lwjgl.opengl.Display;
import static org.lwjgl.opengl.GL11.*;
import org.lwjgl.Sys;

public class FPCameraController{
	//3d vector to store cameras position
	private Vector3f position = null;
	private Vector3f lPosition = null;
	
	//rotation around Y axis of the camera
	private float yaw = 0.0f;
	//rotation around the X axis of the camera
	private float pitch = 0.0f;
	private Vector3Float me;
	
	//Constructor
	public FPCameraController(float x, float y, float z){
		//instantiate position Vector3f to the x y z params
		position = new Vector3f(x,y,z);
		lPosition = new Vector3f(x,y,z);
		lPosition.x = 0f;
		lPosition.y = 15f;
		lPosition.z = 0f;
	}
	
	//Increment camera's current yaw rotation (left and right rotation)
	public void yaw(float amount){
		yaw += amount;
	}
	
	//increment the camera's current pitch rotation
	public void pitch(float amount){
		pitch -= amount;
	}
	
	public void walkFoward(float distance){
		float xOffset = distance * (float)Math.sin(Math.toRadians(yaw));
		float zOffset = distance * (float)Math.cos(Math.toRadians(yaw));
		position.x -= xOffset;
		position.z += zOffset;
	}
	
	public void walkBackward(float distance){
		float xOffset = distance * (float)Math.sin(Math.toRadians(yaw));
		float zOffset = distance * (float)Math.cos(Math.toRadians(yaw));
		position.x += xOffset;
		position.z -= zOffset;
	}
	
	public void strafeLeft(float distance){
		float xOffset = distance * (float)Math.sin(Math.toRadians(yaw - 90));
		float zOffset = distance * (float)Math.cos(Math.toRadians(yaw - 90));
		position.x -= xOffset;
		position.z += zOffset;
	}
	
	public void strafeRight(float distance){
		float xOffset = distance * (float)Math.sin(Math.toRadians(yaw + 90));
		float zOffset = distance * (float)Math.cos(Math.toRadians(yaw + 90));
		position.x -= xOffset;
		position.z += zOffset;
	}
	
	public void moveUp(float distance){
		position.y -= distance;
	}
	
	public void moveDown(float distance){
		position += distance;
	}
	
	//translates and rotates the matrix so that it looks through the camera
	//basically does what gluLookAt() does
	public void lookThrough(){
		//rotate pitch around X axis
		glRotatef(pitch, 1.0f, 0.0f, 0.0f);
		//rotate yaw around Y axis
		glRotatef(yaw, 0.0f, 1.0f, 0.0f);
		//translate to the position vector's location
		glTranslatef(position.x, position.y, position.z);
	}
	
	public void gameLoop(){
		FPCameraController camera = new FPCameraController(0,0,0);
		float dx = 0.0f;
		float dy = 0.0f;
		//length of frame (delta time)
		float dt = 0.0f;
		//When the last frame was
		float lastTime = 0.0f;
		long time = 0;
		float mouseSensitivity = 0.09f;
		float movementSpeed = 0.35f;
		//Hide mouse
		Mouse.setGrabbed(true);
		
		//Keep looping until display window is closed
		while (!Display.isCloseRequested() && !Keyboard.isKeyDown(Keyboard.KEY_ESCAPE)){
			time = Sys.getTime();
			lastTime = time;
			
			//distance in mouse movement from last getDX call
			dx = Mouse.getDX();
			dy = Mouse.getDY();
			
			//control camera yaw from x movement 
			camera.yaw(dx * mouseSensitivity);
			camera.pitch(dy * mouseSensitivity);
			
			//Movement
			if (Keyboard.isKeyDown(Keyboard.KEY_W)){
				camera.walkFoward(movementSpeed);
			}
			if (Keyboard.isKeyDown(Keyboard.KEY_S)){
				camera.walkBackwards(movementSpeed);
			}
			if (Keyboard.isKeyDown(Keyboard.KEY_A)){
				camera.strafeLeft(movementSpeed);
			}
			if (Keyboard.isKeyDown(Keyboard.KEY_D)){
				camera.strafeRight(movementSpeed);
			}
			if (Keyboard.isKeyDown(Keyboard.KEY_SPACE)){
				camera.moveUp(movementSpeed);
			}
			if (Keyboard.isKeyDown(Keyboard.KEY_E)){
				camera.moveDown(movementSpeed);
			}
			
			//set modelview matrix back to identity
			glLoadIdentity();
			//Look through camera before drawing
			glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
			//DRAW SCENE HERE
			render();
			//draw buffer to the screen
			Display.update();
			Diaplay.sync(60);
		}
		Display.destroy();
	}
	
	private void render(){
		try{
			glBegin(GL_QUADS);
				glColor3f(1.0f, 0.0f, 1.0f);
				glVertex3f(1.0f, -1.0f, -1.0f);
				glVertex3f(-1.0f,-1.0f,-1.0f);
				glVertex3f(-1.0f, 1.0f,-1.0f);
				glVertex3f( 1.0f, 1.0f,-1.0f);
			glEnd();
		}
		catch(Exception e){
		
		}
	}
}
```
