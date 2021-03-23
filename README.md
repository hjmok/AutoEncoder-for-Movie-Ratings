# AutoEncoder-for-Movie-Ratings

For this project, an AutoEncoder model predicts what rating a user will give to a film.

## Dataset and Library
PyTorch was the main module used for this model.
The dataset consisted of 1 million rows of movie ratings from 6040 users across 3952 films. The ratings ranged from 1 (lowest) to 5 (highest).
Please find the dataset from Grouplens under 'MovieLens 1M Dataset':

https://grouplens.org/datasets/movielens/

## AutoEncoders Overview
An AutoEncoder is a self-supervising learning algorithm, where the output label is the same as the original input. This means the goal is to have the output match the input, therefore the number of input nodes and output nodes are the same. As such, purpose of the hidden nodes is to extract and encode key features about the input, then decode it to the output. However, this means that the number of hidden nodes cannot exceed the number of input nodes. This is because the model will not learning any key features about the inputs, instead have each hidden node associated directly with an input node.

The ability to match outputs with the original inputs makes AutoEncoders great recommendation systems. Using this project as an example, the AutoEncoder model would get the ratings of each user for a variety of different movies as the inputs. If the model can match the output ratings with the inputs accurately, that means the hidden nodes were able to extract key features about the films that made the user enjoy it. The features will not be specifically labeled, however they may be inferred to have common traits, such as being the same genre, having certain directors or actors, etc. For this project, a Stacked AutoEncoder was used, which just involves more than 1 hidden layer.

For more details, please read the following paper from Stanford about AutoEncoders:

http://ufldl.stanford.edu/tutorial/unsupervised/Autoencoders/

## Results
After 500 epochs, the training and test losses achieved were 0.8077 and 0.8958 respectively. This means that the Stacked AutoEncoder model was able to accurately predict the rating a user would give to a film within ±1 star.

To further improve the model, the number of nodes in the hidden layers as well as the number of hidden layers can be experimented with. In addition, dropout layers may be useful to prevent overfitting of the model.

For the more detailed explanations with image, please visit: https://hjmok.github.io/josephmok_portfolio/#/AE
