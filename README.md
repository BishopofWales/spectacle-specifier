# spectacle-specifier
Experimenting with Keras and stylegan2. Main finding with stylegan was a method for extracting a large sample of faces with one common feature (in this case glasses). The first step was to find a
pool of faces that had glasses and save their latent vectors. By interpolating between two faces with glasses, we can generate new faces that are likely to have glasses. 

My novel idea was to interpolate between three latent vectors instead. Instead of sampling from a line, we're sampling from a triangle embedded in 512 dimensional space. The resulting algorithm 
did correctly produce faces with glasses. 

I neither found nor looked for a performance increase compared to the simple linear interpolation. However I would be curious to see such a method scaled up for more dimensions. Instead of randomly sampling from a triangle,
why not a tetrahedron? For n samples, you could create an n-1 dimensional shape, n points being the minimum number of points required to define a solid in n-1 dimensions. The math to do this beyond at this time. 

UPDATE: Turns out the simplest shape in n-dimensional space has a name, it's called a simplex. Here's a paper which shows how to randomly sample from one:
https://www.cs.cmu.edu/~nasmith/papers/smith+tromble.tr04.pdf
