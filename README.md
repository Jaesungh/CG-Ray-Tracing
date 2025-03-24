# CG-Ray Tracing

In this assignment, I implemented simple ray tracer, rendering scene cosisting of a plane and three spheres, and shaded them with Phong model.
## result 
![image](https://github.com/user-attachments/assets/513fb8c1-4252-4f20-9fc3-071faba7b80f)

Light in this result is at position of (15,15,15) so you can alter the light by changing its position
```c++
 Light light(vec3(15, 15, 15), vec3(1, 1, 1)); // White light at position (15, 15, 15)
```
These are phong model coefficients that I applied on this result, altering it could get different result of image.   
```c++
	float ambientStrength = 0.1f;
	float diffuseStrength = 0.8f;
	float specularStrength = 0.5f;
```
Changes to these Plane() and Sphere() would alter the coordinates, size, and color. 
For example spheres can result in white (I may have misunderstood the one of the clause on slide for assignment incorrect) :
![image](https://github.com/user-attachments/assets/9bac44c1-e83e-4123-8b3d-1f38288a593b)

```c++
		planes.push_back(Plane(vec3(0.0f, 1.0f, 0.0f), -2.0f, vec3(0.5f, 0.5f, 0.5f))); // plane located at y = -2 (gray)
		spheres.push_back(Sphere(vec3(-4.0f, 0.0f, -7.0f), 1.0f, vec3(1.0f, 0.0f, 0.0f))); // s1 (red)
		spheres.push_back(Sphere(vec3(0.0f, 0.0f, -7.0f), 2.0f, vec3(0.0f, 1.0f, 0.0f))); // s2 (green)
		spheres.push_back(Sphere(vec3(4.0f, 0.0f, -7.0f), 1.0f, vec3(0.0f, 0.0f, 1.0f))); // s3 (blue)
```

## Compilation & run instructions 
Tested on Visual Studio 2022. 

![image](https://github.com/user-attachments/assets/2827364c-67cc-45e5-bc3b-4ee531f562d2)

-Build - Build Solution (F7)

-Debug - Start Debugging (F5)

You may compile using preffered c++ compiler with OpenGL support.

## Short description of the code
#### classes :

##### Ray :
Ray ()  : default constructor initializing origin and direction to (0,0,0) and Ray(const vec3& o, const vec3& d) specifying origin and direction
##### Camera : 
Camera () : Camera parameters including eye position, view, dimensions, and resolution.
Ray generateRay(int i, int j) : Generates ray for the given pixel coords.
##### Plane :
Plane(const vec3& n, float d, const vec3& col) : Initialize a plane.
bool intersect(const Ray& ray, float& t) : Checks for intersection with a given ray.
##### Sphere :
Sphere(const vec3& c, float r, const vec3& col) : Initialize a sphere
bool intersect(const Ray& ray, float& t) : Check for intersection with a given ray and spheres.
##### Light :
Light(const vec3& pos, const vec3& col): Set light position and color.
##### Scene : 
Scene() : Initialiez the scene with plane and spheres.
bool intersect(const Ray& ray, float& t, vec3& color, vec3& normal) : Checks for intersection of ray-object.

#### Functions :

phongShading : computes lighting using the Phong model. 
render : creates the final image by casting rays and computing colors. Over each pixel, generating a ray and check for intersections.

## References : 

https://learnopengl.com/

https://github.com/ADoublePlus/Ray-Tracing

https://github.com/genericalexacc/RayTracing

https://raytracing.github.io/
