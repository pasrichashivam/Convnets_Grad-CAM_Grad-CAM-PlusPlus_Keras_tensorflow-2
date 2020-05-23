## This Repository is implementation of Algorithms which gives the Visual Explainations for the decisions made by CNN's Using Tesorflow-2.
### Below are the algorithms implemented
1. **CAM: (Class Activation Maps).** 
	* **Link**:https://arxiv.org/pdf/1512.04150.pdf

#### Brief of CAM.
* This algorithm works with CNN having a large number of Convolutional layers and before the final classification(output) layer it performs global average using Global Average Pooling layer.
* So CAM works with the architecture having (Convolutional Layer -> Global Average Pooling -> Dense layer with softmax) as the final 3 layers.
###### Disadvatage of CAM
* The above specific combination of last 3 layers of CNN avoid CAM to be applied to variety of Network Architectures.
* CAM cannot be used to Explain class specific features.
![CAM (Class Activation Mapping)](Images/CAM.png?raw=true "CAM") 

2. **Grad-CAM: (Gradient Based Class Activation Mapping)**
	* **Link**:https://arxiv.org/pdf/1610.02391.pdf
	
![Grad-CAM (Gradient Based Class Activation Mapping)](Images/GRAD_CAM.png?raw=true "Grad-CAM") 
* Grad-CAM uses the gradients of any target class (e.g. tigercat) flowing into the final Convolutional
layer to produce the feature map highlighting the important regions in the image responsible for provided target class (e.g. tigercat)
* Unlike CAM, Grad-CAM is applicable to a wide variety of CNN models.
###### Disadvatage of Grad-CAM.
* It does not give good results if there are multiple objects of the same target class in an image.
 
3. **Grad-CAM++: (Improved version of Grad-CAM)**
	* **Link**:https://arxiv.org/pdf/1710.11063.pdf

![Grad-CAM++](Images/GRAD_CAM_PP.png?raw=true "Grad-CAM++") 
* Grad-CAM++ solves the disadvantage of Grad-CAM by introducing the new equation (a <sup>kc</sup><sub>ij</sub>) created by using the higher order derivatives (first, second & third derivative) flowing to the Convolution layer.
* This equation is then combined with the equation of Grad-CAM and follow the same architecture as in Grad CAM.
* Grad-CAM is also applicable to a wide variety of CNN models.
* It gives good results even if there are multiple objects of the same target class in an image.
