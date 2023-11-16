**Pseudo code for ray casting:**
For each pixel 
	find the ray from the eye through the pixel
	for each object in the scene
		if the ray intesects the objects, and is closest yet
			record the intersection and object
	find color for the closest intersection