# RecommendationSystem_PredictMovieRatings

πΏ=minπ,π,{π’π}ππ=1,{π£π}ππ=1πΌ(βπβππ£2ππ+βπβππ’2ππ+βππ2π+βππ2π)+βπ,πβξ΅train(π¦ππβπβππβππβπ’πππ£π)2

π  : scalar mean rating

ππ  : scalar bias term for user  π 

ππ  : scalar bias term for movie  π 

π’π  : K-dimensional vector for user  π 

π£π  : K-dimensional vector for movie  π

Construct adjacency matrix with the given data, assuming its weighted un-directed bi-partited graph and the weight of each edge is the rating given by user to the movie

we can construct this matrix like  π΄[π][π]=πππ  here  π  is user_id,  π  is movie_id and  πππ  is rating given by user  π  to the movie  π 
Hint : we can create adjacency matrix using csr_matrix

We will Apply SVD decomposition on the Adjaceny matrix link1, link2 and get three matrices  π,β,π  such that  πΓβΓππ=π΄ ,
if  π΄  is of dimensions  πΓπ  then
U is of  πΓπ ,
β  is of  πΓπ  and
π  is  πΓπ  dimensions.

*. So the matrix  π  can be represented as matrix representation of users, where each row  π’π  represents a k-dimensional vector for a user

*. So the matrix  π  can be represented as matrix representation of movies, where each row  π£π  represents a k-dimensional vector for a movie.

Compute  π  ,  π  represents the mean of all the rating given in the dataset.(write your code in def m_u())

For each unique user initilize a bias value  π΅π  to zero, so if we have  π  users  π΅  will be a  π  dimensional vector, the  ππ‘β  value of the  π΅  will corresponds to the bias term for  ππ‘β  user (write your code in def initialize())

For each unique movie initilize a bias value  πΆπ  zero, so if we have  π  movies  πΆ  will be a  π  dimensional vector, the  ππ‘β  value of the  πΆ  will corresponds to the bias term for  ππ‘β  movie (write your code in def initialize())

Compute dL/db_i (Write you code in def derivative_db())

Compute dL/dc_j(write your code in def derivative_dc()

Printing the mean squared error with predicted ratings.

π¦Μ ππ=π+ππ+ππ+dot_product(π’π,π£π)
