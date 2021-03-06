In the recent years deblurring of motion blurred images has been intensively
researched. These works can be divided into single image deblurring and multi-
image deblurring. Furthermore they can be distinguished by their assumption on
blur kernels: spatially uniform or non-uniform blur kernels and known or unkown
PSFs.

Several approaches were proposed for single image deblurring with an unknown blur 
kernel. The majority of these algortihms use statistical models for the necessary
kernel estimation :cite:`Fergus2006`, :cite:`Levin2011`. Some of
them improved the estimation by considering the presence of sharp edges in unblurred images
:cite:`Joshi2008`, :cite:`Cho2009`, :cite:`Xu2010`,
:cite:`Shan2008`. A method to improve estimated PSFs is shown by Zhu
*et al.* :cite:`Zhu2012` where the PSF is also deconvolved because it is
affected by blur itself. In non-blind deconvolution where the PSF is known sparse
natural image priors were used to improve image restoration :cite:`Levin2007`.

These methods assumes that all pixels are blurred with the same (uniform) blur
kernel. However blur at a specific position is highly correlated with camera
motion and the corresponding scene depth. This results in a spatially non-
uniform kernel. Joshi *et al.* :cite:`Joshi2010` discussed the spatial
variance of PSFs which is correlated to rotational and translational camera
motion. Whereas the spatial variance caused by rotation is depth independent
and that caused by translation depends on scene depth.

Some methods deals with rotation blur models such as Shan *et al.*
:cite:`Shan2007` and Whyte *et al.* :cite:`Whyte2010`. A simplified camera
motion model were also introduced by Gupta *et al.* :cite:`Gupta2010`. However
camera translation which causes significant image blur is not handled in these
approaches. Because translation depends on scene depth some works already
computed depth maps by multi-image approaches. Favaro *et al.*
:cite:`Favaro2004` modeled motion blur and defocus blur of a scene from a
collection of blurred images. Sorel *et al.* :cite:`Sorel2008` proposed an
algorithm estimating a sharp image and a depth map simultaneously, based on
the minimization of a cost function. It uses multiple blurred images and a
user selection of a region of constant depth as input. Ji *et al.*
:cite:`Ji2012` on the other hand introduced a region based method to remove
spatially-varying blur from a single photograph. Another algorithm from Hu
:cite:`Hu2014` works on a single image and provides a unified layer-based
model for depth-involved deblurring.

There are also works that take both rotation and translation into
consideration like Joshi *et al.* :cite:`Joshi2010` where an inertial sensor is
used to measure the camera motion. Tai *et al.* :cite:`Tai2010` used labeled
cues to estimate the camera motion. Bae *et al.* :cite:`Bae2013` combined a
depth sensor (Microsoft Kinect) and an inertial sensor to recover the real
camera movement and estimate the spatially-variant blur kernel and the latent
image. Yue *et. al.* :cite:`Yue2014` proposed a method to restore the
unblurred image of a large-depth-range scene deteriorated by arbitrary camera
motion with a single image and a given stereo map. These approaches have the
limitations that they either need external input like user interactions or
hardware or they simplify the camera parameters.

There are also works focused on removal of spatially variant blur caused by
object motion :cite:`Jia2007`, :cite:`Chak2010`, :cite:`Kobayashi2014`. This
is more difficult as blur per object can be completely different. So we
restrict the setup to motion blur caused by camera shake and depth estimated
from a stereo image pair of a scene with depth-variations.
