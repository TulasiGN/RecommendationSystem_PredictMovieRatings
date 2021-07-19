# RecommendationSystem_PredictMovieRatings

𝐿=min𝑏,𝑐,{𝑢𝑖}𝑁𝑖=1,{𝑣𝑗}𝑀𝑗=1𝛼(∑𝑗∑𝑘𝑣2𝑗𝑘+∑𝑖∑𝑘𝑢2𝑖𝑘+∑𝑖𝑏2𝑖+∑𝑗𝑐2𝑖)+∑𝑖,𝑗∈train(𝑦𝑖𝑗−𝜇−𝑏𝑖−𝑐𝑗−𝑢𝑇𝑖𝑣𝑗)2

𝜇  : scalar mean rating

𝑏𝑖  : scalar bias term for user  𝑖 

𝑐𝑗  : scalar bias term for movie  𝑗 

𝑢𝑖  : K-dimensional vector for user  𝑖 

𝑣𝑗  : K-dimensional vector for movie  𝑗

Construct adjacency matrix with the given data, assuming its weighted un-directed bi-partited graph and the weight of each edge is the rating given by user to the movie

we can construct this matrix like  𝐴[𝑖][𝑗]=𝑟𝑖𝑗  here  𝑖  is user_id,  𝑗  is movie_id and  𝑟𝑖𝑗  is rating given by user  𝑖  to the movie  𝑗 
Hint : we can create adjacency matrix using csr_matrix

We will Apply SVD decomposition on the Adjaceny matrix link1, link2 and get three matrices  𝑈,∑,𝑉  such that  𝑈×∑×𝑉𝑇=𝐴 ,
if  𝐴  is of dimensions  𝑁×𝑀  then
U is of  𝑁×𝑘 ,
∑  is of  𝑘×𝑘  and
𝑉  is  𝑀×𝑘  dimensions.

*. So the matrix  𝑈  can be represented as matrix representation of users, where each row  𝑢𝑖  represents a k-dimensional vector for a user

*. So the matrix  𝑉  can be represented as matrix representation of movies, where each row  𝑣𝑗  represents a k-dimensional vector for a movie.

Compute  𝜇  ,  𝜇  represents the mean of all the rating given in the dataset.(write your code in def m_u())

For each unique user initilize a bias value  𝐵𝑖  to zero, so if we have  𝑁  users  𝐵  will be a  𝑁  dimensional vector, the  𝑖𝑡ℎ  value of the  𝐵  will corresponds to the bias term for  𝑖𝑡ℎ  user (write your code in def initialize())

For each unique movie initilize a bias value  𝐶𝑗  zero, so if we have  𝑀  movies  𝐶  will be a  𝑀  dimensional vector, the  𝑗𝑡ℎ  value of the  𝐶  will corresponds to the bias term for  𝑗𝑡ℎ  movie (write your code in def initialize())

Compute dL/db_i (Write you code in def derivative_db())

Compute dL/dc_j(write your code in def derivative_dc()

Printing the mean squared error with predicted ratings.

𝑦̂ 𝑖𝑗=𝜇+𝑏𝑖+𝑐𝑗+dot_product(𝑢𝑖,𝑣𝑗)
