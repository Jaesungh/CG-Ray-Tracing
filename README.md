# CG-Ray Tracing

In this assignment, I implemented simple ray tracer, rendering scene cosisting of a plane and three spheres.
## Result 
Result image :

By default, the code outputs a black-and-white image:
- **White** for pixels where the ray intersects an object
- **Black** otherwise
 
![image](https://github.com/user-attachments/assets/d5563686-0ef1-4161-9472-4232aaace29c)

It may look slightly off-center locating at left to center due to different ratio between window and camera. 

When width and height of window are changed to 512x512, not 1280x720. Result looks like this, the biggest sphere locating in the center of the window. 

![image](https://github.com/user-attachments/assets/e541edd9-f2f9-4c58-9954-bbb98867d26c)



## Compilation & run instructions 
Tested on Visual Studio 2022. 

![image](https://github.com/user-attachments/assets/2827364c-67cc-45e5-bc3b-4ee531f562d2)

-Build - Build Solution (F7)

-Debug - Start Debugging (F5)

You may compile using preffered c++ compiler with OpenGL support.

## Short description of the code
### classes :

#### Ray :
Ray ()  : default constructor initializing origin and direction to (0,0,0) and Ray(const vec3& o, const vec3& d) specifying origin and direction
#### Camera : 
Camera () : Camera parameters including eye position, view, dimensions, and resolution.
Ray generateRay(int i, int j) : Generates ray for the given pixel coords.
#### Plane :
Plane(const vec3& n, float d, const vec3& col) : Initialize a plane.
bool intersect(const Ray& ray, float& t) : Checks for intersection with a given ray.
#### Sphere :
Sphere(const vec3& c, float r, const vec3& col) : Initialize a sphere
bool intersect(const Ray& ray, float& t) : Check for intersection with a given ray and spheres.
#### Light :
Light(const vec3& pos, const vec3& col): Set light position and color.
#### Scene : 
Scene() : Initialiez the scene with plane and spheres.
bool intersect(const Ray& ray, float& t, vec3& color, vec3& normal) : Checks for intersection of ray-object.

### Functions :
render : creates the final image by casting rays and computing colors. Over each pixel, generating a ray and check for intersections.

## References : 

https://learnopengl.com/

https://github.com/ADoublePlus/Ray-Tracing

https://github.com/genericalexacc/RayTracing

https://raytracing.github.io/

Assistance from Github Copilot
