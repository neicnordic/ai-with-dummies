<img src="source/logo.png" alt="logo" width="200"/>

# The Game

AI for dummies is a game to teach how neural networks work on a most basic level. Each instance on the game has 5 participants who will act out the training of a neural network. The purpose of the game is to get a deeper understanding of what's actually happening when neural networks are trained, and how they work in practice.

The neural network that this game aims to train is meant to take a 3x4 pixel image and detect if the image shows a number "1".

The game is expected to take 30-45 minutes with setup time. It's encouraged to run this game simultaneously as you explain the concepts behind neural networks.

## Setup of the game

You will need 5 people for this game, 4 will act as a hidden layer in the network and 1 person acts acts out the ouput layer. The input layer will be automatically handled by the game rules.

Print out the material in the print_out_cards.pdf. After this you should have:

* 3 x 4 stacks of paper in different colors, with "-1", "0", and "1" printed on them, signifying the weights between the input layer and the hidden layer.
* 4 papers with "1" on them, signifying the weights between the hidden layer and the input layer.
* 12 lightbulbs signifying the signals to the input layer.
* 8 double sided papers, with one side green, and the other side red.
* Two signal cards for the output layer for training.
* A printout of the training and verification data, if you don't have access to a screen to display this data to the participants.

Place the input layer weight papers, all with the paper with the "0" on top as shown in the picture below. One player will handle each color. Place a lightbulb paper in front of each stack.

Place the output layer weight papers as shown in the image.

Get the participants of the game, and place them according to the image. Of the 4 players handling the input layer, the first one will handle the input of the 3 pixels of the first row, the second player will handle the input for the second row, etc.

## Basic rules

When an image is processed by the neural network, if the result is 2 or more, the image is assumed to represent the number "1". If it's 1 or under, it's assumed not to represent the number "1". This is called the "Activation function". 

If a bulb is turned face up, it's counted as a 1, and if it's turned face down it's counted as a 0.

## Playing the game - Training

The first task is to train the network.

 1. Place the next image in front of the participants, or on the screen.
 2. Turn the lightbulb images so that each colored pixel has the lightbulb showing, and the blank pixels have the lightbulb turned face down.
 3. Now, each of the 4 players takes each of their inputs, and multiplies them with the weight. The result is added together and signaled to the next layer by showing the appropriate cards. Green cards for positive numbers, red cards for negative. In the first round, all weights are 0, so all results will be 0.
 4. The output layer person sums all signals together. If the result is 2 or more, the network has detected this as a 1.
 5. The output layer person checks this aganist the expected result.
    - If the network detected it correctly, no further action is taken, and we'll move to the next data point (go to 1).
    - If the network falsly detected that the input represented a "1", even if it was not, a -1 will be sent back to the network.
    - If the network did not detect that the number represented a "1", even if it was, a 1 will be sent back to the network.
 6. Now we'll train the network, and do "back propagation". The output layer person takes the appropriate number (1, or -1), and shows it to the people who most contributed to the error (gave most positive numbers if the input did not represent a 1, or gave the most negative numbers if the input represented a 1)
 7. Each person who got a the signal from the output layer adds or subtracts 1 from each input which has a signal (lightbulb).
 8. To see that the training worked, go to point 3. 
 
When you are out of training data, you have a trained network. The real value of the network are the weights that are assigned. These make up the "trained" network.

## Data classification

Now you're ready to see how your network does! Take the first piece of verification data, and do the exact same steps of training, except the back propagation. Take an image, and see if yor network think it represent s a "1" or not!


## Competition mode

Take two teams. Choose a number between 0-9. Each team creates 3 pieces of training data and trains a network. Take the data for the corresponding number under the "extra_data" folder, and run it through each network. The team the classifies more samples correctly wins!   
## Caveat emptor

Obviously, real neural network implementations are more complicated than the simplified model presented in the game. In reality backpropagation is more of a descriptive name for the application of chain rule to the derivative of the loss function. Important concepts to understand are gradient descent, loss function and activation function. To get a deeper understanding of neural networks, a recommended read is this nice and educational article: https://ayearofai.com/rohan-lenny-1-neural-networks-the-backpropagation-algorithm-explained-abf4609d4f9d
