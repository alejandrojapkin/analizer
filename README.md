# analizer
Image analysis , retinal characterisation engine.

Pipeline:

Image optimizacion -> Analysis phase -> Storage


1 - Optimization.

Implementation of Lattice Regression (see Maya Gupta's paper ICC profiling)
As foreshadowed in the introduction, the main idea behind the proposed lattice regression is to choose output colors for LUT gridpoints that interpolate the training data accurately. That is, given a training sample input color (e.g. a L*a*b* value), the output color (e.g. device RGB value) interpolated from the LUT should be close to the known training sample output (RGB) color. The key insight is that if a linear interpolation technique (e.g. tri- linear, pyramidal, or tetrahedral interpolation) is used on the LUT, the operation can be inverted to solve for the node outputs that minimize the squared error of the training data. However, unless the LUT is populated with ample training data, this solution will not necessarily be unique. Furthermore, due to device and mea- surement noise, it may be beneficial to avoid fitting the training data exactly. For these reasons, two forms of regularization are added. In total, the proposed form of lattice regression trades off three terms: empirical risk, Laplacian regularization, and global bias. 
