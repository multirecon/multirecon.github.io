---
title: About the Project
permalink: /about
background: /assets/img/ct-mri-pet.png

---




## Context: Multimodal Medical Imaging  


Medical imaging is the technique of creating a visual representation of the anatomy or the function of some organs or tissues. Medical images are obtained in two steps: (i) measurement data acquisition by a scanner and (ii) image reconstruction from the measurement data—an ill-posed inverse problem.
{: style="text-align: justify"}

In computed tomography (CT), the image corresponds to X-ray attenuation, which reflects the proportion of X-ray photons scattered or absorbed as they pass through the object. Rotating systems such as helical CT collect three-dimensional (3-D) information, thus allowing the reconstruction of a 3-D volumetric image of the anatomy. In positron emission tomography (PET), the image to reconstruct is the activity distribution of a radiotracer delivered to the patient. The radiotracer tracks the distribution of a substance within a natural system such as a cell or tissue (e.g., tumors) or fluid flow (e.g., blood perfusion). The system detects pairs of γ-rays emitted in opposite directions indirectly from the positron-emitting radiotracer; each detected pair defines a line of response on which the γ-emission has occurred. In magnetic resonance imaging (MRI), a strong magnetic field and computer-generated radio waves are used to produce images whose contrast depends on the mobile proton density and the tissue relaxation times. It offers a good contrast in the soft tissues, higher than with CT. MRI is not limited to the structure and can also provide functional information.
{: style="text-align: justify"}

PET/CT and PET/MRI multimodal systems can join the functional information of the PET and the anatomical information of the CT and the MRI, for example in oncology to quantify the degree of severity of a tumor (function) and to localize it (anatomy), or in brain imaging to monitor the progression of Alzheimer disease. Because of their complementary, all PET systems are nowadays combined either with CT of MRI. In addition, the CT or the MRI data can provide the attenuation map (μ-map) needed for PET attenuation correction, which is a mandatory step for quantitative PET imaging.
{: style="text-align: justify"}

## Improving Image Quality


The measurement data may suffer from poor signal-to-noise ratio (SNR). This translates after image reconstruction into degraded image quality and degraded quantification accuracy. In CT and PET, the SNR is mostly affected by the number of emitted photons (patient dose) and the detector response (sensitivity), while in MRI the SNR is dictated by the scanning time. Therefore, there is a trade-off between sufficiently high SNR measurement data on one side, and shorter acquisitions and lower patient dose on the other side. Furthermore, as PET/CT and PET/MRI acquisitions require sufficient time (from several seconds in CT to several minutes in PET), they suffer from motion blur and activity/attenuation misalignment artifacts in the reconstructed images, and must be compensated for. Motion compensation techniques estimate the time-dependant motion field and require to consider the measured data as a function of position and of the extra time dimension which in practice is achieved by splitting the data in short time frame with poor SNR. Similarly, in dynamic PET imaging, the kinetic parameters of the radiotracer in the targeted tissues are also estimated by considering the measured data as a function of time, resulting in low SNR levels in each time frames. The challenge of image reconstruction is therefore to reconstruct accurate images from a short and low-dose acquisition with acceptable noise level. This is usually achieved in two ways:
{: style="text-align: justify"}
 - by increasing the system sensitivity (hardware);
 - with the utilization of image reconstruction techniques that can control the noise while preserving the resolution (software).
 {: style="text-align: justify"}


## Our Project


**MultiRecon** will explore a third way: the utilization of combined imaging modalities to exploit joint information between the images (hardware+so tware) for multimodal image reconstruction, with an emphasis on PET/CT and PET/MRI hybrid systems.
{: style="text-align: justify"}

Over the last decades, new methodologies have pushed towards less noisy reconstructions with lower patient dose. “Noise-controlling” reconstruction methods have been developed since the 80’s; starting with model-based image reconstruction (MBIR) iterative techniques (maximum likelihood) that account for the measurement statistics such as the expectation-maximization (EM) algorithm, then including a penalty term (regularizer) to control the noise while preserving image edges. More recently, compressed sensing techniques utilize the sparsity to solve underdetermined systems; these techniques are nowadays used for sparse-view and low-dose CT reconstruction, with total variation regularizers. Sparse priors in the wavelet domain have also been employed within reconstruction  to preserve essential features of the images while denoising.
{: style="text-align: justify"}

Recent artificial intelligence (AI) techniques for image reconstruction have pushed this principle further by learning adapted representations instead of using “fixed” representations. More particularly, with a training dataset of existing images, it is possible to train a model to learn image features that can be used to reconstruct new images, with the help of machine learning (ML) techniques such as dictionary learning (DL) and deep learning. 
{: style="text-align: justify"}



Conventional image regularizers—i.e., non AI-based—have been extended to multimodal imaging. When the different channels share some structural information, a coupled regularization is indeed highly beneficial for multichannel imaging. This is the case in PET/CT and PET/MRI as each modality depends on the same underlying anatomy. However these methods utilize hand-crafted objective functions that may not reflect the natural dependencies between the modalities.
{: style="text-align: justify"}

Optimal image coupling models can be learned with AI techniques such as multimodal machine learning. These techniques are utilized to learn abstract models that can process and relate information from multiple modalities, unlike conventional techniques where dependencies between modalities are imposed by a given analytical model. For exemple, multimodal dictionary learning (MDL) aims at determining multimodal dictionaries that can provide a joint sparse representation of the multimodal images: each atom does not only carry individual information for each modality individually but also inter-modality information. By reconstructing multimodal images using MBIR techniques coupled with MDL, the multimodal information can be optimally utilized by allowing the image modalities to “talk to each other” during the reconstruction process through the learned multimodal dictionaries, thus reducing the noise while preserving image resolution.
{: style="text-align: justify"}

Thanks to the noise reduction allowed by the exploitation of the dependencies between the images, a reduction of the patient dose and of the acquisition time can be foreseen with multimodal image reconstruction with AI: dependencies across modalities will be learned by the model—as opposed to previous work in which multi-modal structural similarities were imposed by the model—and could be extended beyond simple geometric similarities, e.g., with the possibility of learning joint textural and emporal information.
{: style="text-align: justify"}

The ambition of **MultiRecon** is to propose new practical (i.e., with low computational cost) AI techniques for simultaneous reconstruction from different modalities, with an emphasis on PET/CT and PET/MRI; these hybrid imaging systems provide both functional and anatomical information which will be jointly exploited by AI.
{: style="text-align: justify"}

**MultiRecon** is funded with a 500,000€ grant from the French National Research Agency (ANR) with grant number ANR-20-CE45-0020. 

<!-- These features take the form of “atoms”, regrouped into successive layes of dictionaries, that are used to sparsely represent the image. DL-based image reconstruction consists in combining the learned atoms with the raw scanner data within a regularized MBIR framework, where the regularizer evaluates the accuracy and the sparsity of the image representation with atoms. -->

<!-- This is the base Jekyll theme. You can find out more info about customizing your Jekyll theme, as well as basic Jekyll usage documentation at [jekyllrb.com](https://jekyllrb.com/)

You can find the source code for Minima at GitHub:
[jekyll][jekyll-organization] /
[minima](https://github.com/jekyll/minima)

You can find the source code for Jekyll at GitHub:
[jekyll][jekyll-organization] /
[jekyll](https://github.com/jekyll/jekyll)


[jekyll-organization]: https://github.com/jekyll -->
