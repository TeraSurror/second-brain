Main Components:
- Convolutional Layer (+ activation function)
- Pooling Layer
- Fully Connected Layers

### Mathematical formula for Convolution:
#### f(x) = x * k(s) = $\int_{R^m} x(r) . k(s - r) dr$
where x: $R^m -> R$ and k: $R^m -> R$ is the kernel function 

### Convolution
we use a matrix to represent a kernel with a fixed support

Hyper-parameters:
- Kernel Size - dims of the kernel
- Stride - Length of the step when sliding the window
- Zero Padding - Whether zeros are added around the boundary

Watch the slide for a visual representation of a convolution in a matrix

### Convolutional Layer
- Exploits sparse local interactions and parameter sharing
- Equivariance to translation
- Multiple feature maps are generated


### Pooling
- provides summary stats of 
Example of max pooling
![[max pooling.png]]








