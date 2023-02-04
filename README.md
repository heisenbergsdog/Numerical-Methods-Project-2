# Numerical-Methods-Project-2

This is the code for a numerical methods problem set. It contains four questions, all relating to using linear algebra to approximate functions in the coding language Julia. The function of focus of this problem set is the sine function and a method similar to a taylor series is used to approximate it.  

First, the code uses the least squares method to approximate the coefficients in the polynomial expansion. Here's the result when going from 0 to pi/2 and using 1001 different x values in the interval. 
<img width="404" alt="sine approximation" src="https://user-images.githubusercontent.com/69444009/216791144-d6bfc0c1-9e96-4fff-a143-db28b13de19b.png">   
It looks pretty good on this interval! But if you look a little further in range, it doesn't quite match up with the sine function so well:
<img width="410" alt="sine approximation 1" src="https://user-images.githubusercontent.com/69444009/216791161-5a1a4291-e94c-4206-8f9a-2f87cb637aa1.png">   
So we see there's somewhat of an error.   
We can calculate this error on the set interval by taking a root mean square approach (average L2 norm). I've plotted the error for different numbers of polynomial terms, and made it a log plot so that we can really see the order of magnitude of the error:   
<img width="392" alt="log error for first sine approx" src="https://user-images.githubusercontent.com/69444009/216791367-a40e60ff-eff6-4381-b497-db8deca9bd9d.png">    
Note that the error increasing and then sort of oscillating is due to floating point error.

Next the code makes an approximation using only antisymmetric polynomials. The error got a bit better as one can see with the comparison of errors. The antisymmetric version is in pink here:   
<img width="397" alt="compare log error antisymmetric sine and normal" src="https://user-images.githubusercontent.com/69444009/216791532-ff4fc4df-bf85-474a-89e7-592661705f8f.png">   

The last part of the project was to find a linear map that takes the coefficients of the sine aproximation and maps them to the coefficients of the derivative of sine. Analytically, one can compare the polynomial approximation to its derivative and make a matrix like so:   
<img width="194" alt="Screenshot 2023-02-04 162537" src="https://user-images.githubusercontent.com/69444009/216791568-99822f42-ba9d-4427-822a-294c63df0504.png">   
Note this is a sparse matrix and the dots represent zeros.   
Applied to the sine approximation, we get a function that appears to be a cosine!   
<img width="406" alt="cosine derivative from coefficients" src="https://user-images.githubusercontent.com/69444009/216791662-9dc97d2e-6e87-4b25-94d4-17418103b53c.png">    
Then we can check out the error of this as compared to the usual cosine for different numbers of polynomial terms: (again it's a log plot)   
<img width="397" alt="error of cosine derivative approx" src="https://user-images.githubusercontent.com/69444009/216791743-fcfa9547-4405-44ab-ac11-089f524c051c.png">
And it looks pretty good!
