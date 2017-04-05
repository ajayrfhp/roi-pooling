# roi-pooling

![Region of Interest Pooling animation](roi_pooling_animation.gif)

This repo contains the implementation of Region of Interest Pooling as a custom TensorFlow operation. The CUDA code responsible for the computations was largely taken from the original Caffe implementation by Ross Girshick.

For more information about RoI pooling you can check out our [blog](https://deepsense.io/region-of-interest-pooling-explained/)

# Requirements

You need to have CUDA and TensorFlow  installed on your system to compile and use the operation. The code was tested with CUDA 8.0 and TensorFlow 0.12.0 and 1.0.0.

Only official Tensorflow releases are currently supported. If you're using a custom built TensorFlow compiled with a different GCC version (i.e. 5.X) you may need to modify the makefile to [enable the new ABI version.](https://gcc.gnu.org/onlinedocs/libstdc++/manual/using_dual_abi.html)

# Install

To compile and install the operation, issue the following commands:

```
python setup.py install
```

# Usage

After successful installation you can use the operation like this:

```python
from roi_pooling.roi_pooling_ops import roi_pooling

# here obtain feature map and regions of interest
rpooling = roi_pooling(feature_map, rois, 7, 7)
# continue the model
```
