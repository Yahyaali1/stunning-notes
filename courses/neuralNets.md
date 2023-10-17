
How do we calculate derivatives in neural networks 

* Derivatives: Change in x with respect to y 
* Backpropagation Derivatives of Output with respect to parameters 
  * Intermediate nodes can use chain rule
  * For sum derivative is 1
    ```
    b = 1
    c = 1  
    a = b + c 
    
    ``` 
  * For multiplication derivative is the other number 

Neuron
* sum(a1w1+a2w2, b): weight and biased already defined
* Take the input (a1,a2)
* activation function called on the output in step 1 
  
Layer
* list of all neurons (initialized with number of input weights and biases)
* Supply all the inputs (a1,a2) to all the neurons
* Layer neuron defined by output 
  * 3 inputs and 1 output means
    * 3 inputs going into single neuron for single output 
    * 

MLP 
* Number of first inputs 
* Array of intermediate layers eg [3, 3, 1] means 3 layer neuron 
* It is re arranged so that that input and out layers are created 
  * [1,3], [3,3] , [3,1]
  * Output = Layer 1 inputs into Layer 2 until last layer
  * eg Layer1(weights)
  * Layer2(Layer1(weights))
  * Layer3(Layer2(Layer1(weights))) 
  * This can be done iteratively 

Loss 

* Single number that determine the performance of neural network 
* mean gradient square loss 
  * (Output - Truth Value) ** 2 -> to ensure that output is positive 
  * Can also take abs value 
* Sum( of all the mean gradient square values) -> we want to reduce this value

Gradient Descend 
We use gradient to add -ve change to the parameter values to converge to better result. 
It needs to be done on all individual parameters

