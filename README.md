# Optical_Flow_GPU_Opencv3
Extracting optical flow based on GPU in Opencv3

### Preface
This code was adapted from https://github.com/feichtenhofer/gpu_flow and we truly appreciate the work of feichtenhofer. 
The most of the detailed information can be seen in that repository. 

### Install Opencv3
My opencv version is 3.4.3. It will appear some problems when making opencv3 according to official documents. It concludes that 
following command is fine.

`cmake -D CMAKE_BUILD_TYPE=Release -D CMAKE_INSTALL_PREFIX=/usr/local -D WITH_CUDA=ON -D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules -D BUILD_TIFF=ON ..`

### Explaination of Output
The defaulted optical flow values are truncated to lie [-20, 20], and mapped to [0, 255] for JPG compression. The outputs are three channels JPG images. BGR of the image represents x, y, and magnitude of the optical flow value, 
respectively.

### Example
./compute_flow --gpuID=0 --type=1 --skip=1 --vid_path xxx --out_path xxx
