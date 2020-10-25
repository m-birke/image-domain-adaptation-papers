# Image Domain Adaptation Papers 17/19

A subset of nice domain adaptation papers with a short depiction. No warranty for correctness! Within an _Unsupervised Domain Adaptation Setting (UDA)_, annotations are available only in the source domain and images in both domains. Presented papers mainly introduce appproaches to solve this issue in the image domain.

## Image-to-Image Translation

Domain Transformation in Image Space

| Abbr. | Paper Title | Publ. | Link | Comment |
|-------|-------------|-------|------|---------|
|DTN| Unsupervised Cross Domain Image Generation | Nov 2016 | [link](https://arxiv.org/abs/1611.02200) | Generates an avatar to a corresponding celeb face. Shared feature space. Cycle consistency. Only one direction. Similiar to UNIT.|
| SimGAN | Learning from Simulated and Unsupervised Images through AdversarialTraining | Dec 2016 | [link](https://arxiv.org/abs/1612.07828) | GAN is a Refiner network (keeps semantic), starting to use img instead of noise as input, using self regularization pixel distance to keep semantic and use sim labels|
| | Unsupervised Image-to-Image Translation with Generative Adversarial Networks |Jan 2017|[link](https://arxiv.org/abs/1701.02676)| Face transformation. Two-step learning method to translate images between different domains. No closed training in one step. Multi-domain ability. 1st generator learns to generate fake samples, 2nd encoder learns to reconstruct noise input of generator|
| UNIT | Unsupervised Image-to-Image Translation Networks | Mar 2017 | [link](https://arxiv.org/abs/1703.00848) | Two coupled VAE-GANs. Fully shared latent space. Cycle consistency. Adapts textures. Unimodal: gaussian latent space. Works for small imgs. Translates both directions.|
| CycleGAN | Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks | Mar 2017 | [link](https://arxiv.org/abs/1703.10593) | Builds on the pix2pix framework. Big images but can loose semantics. No VAE. Difference to pix2pix: translation in both directions (cycle loss)|
| cdGAN| Conditional Image-to-Image Translation |May 2018|[link](https://arxiv.org/abs/1805.00251)| Two gans: dual gan. Learns separated domain-independent and domain-specific features. No style sampling possible but different target images are possible with different style targets. |
|DCAN|Dual Channel-wise Alignment Networks for Unsupervised Scene Adaptation|Apr 2018|[link](https://arxiv.org/abs/1804.05827)|Channel-wise feature alignment in the generator and segmentation networks. Can extend other image translation models.|
|| Learning image-to-image translation using paired and unpaired training samples | 2018 | [link](https://arxiv.org/abs/1805.03189) | Using paired and unpaired data during training in a two-stage process. Overall 4 Discriminators |
|---------|__In combination with classification__||
| PixelDA | Unsupervised Pixel–Level Domain Adaptationwith Generative Adversarial Networks | Dec 2016 | [link](https://arxiv.org/abs/1612.05424) | Decoupling from the Task-Specific Architecture. No latent space, no encoder.|
||Generate to Adapt|Apr 2017|[link](https://arxiv.org/abs/1704.01705)| GAN: target domain is translated into source domain (_source domain determines feature space!_). Classfication task on embedding.|
|---------| __In combination with segmentation__ |
|I2IAdapt     | Image to Image Translation for Domain Adaptation |  Dec 2017 | [link](https://arxiv.org/abs/1712.00479) | Similar to UNIT/CycleGAN. Two GANs, cycle consistency, fully shared latent space, segmentation task on latent space.|
||Learning from Synthetic Data: Addressing Domain Shift for Semantic Segmentation|Nov 2017|[link](https://arxiv.org/abs/1711.06969)| Simultaneous training of image generation (from feature map) and segmentation in latent space. One GAN, fully shared latent space.|
| CyCADA | Cycle Consistent Adversarial Domain Adaptation | Nov 2017 | [link](https://arxiv.org/abs/1711.03213)  |  Segm. on image space. Cycle consistency, adversarial learning on images and features. Semantic consistency loss on stylized source image. |
|SPIGAN|Privileged Adversarial Learning from Simulation|Oct 2018|[link](https://arxiv.org/abs/1810.03756)|Using depth maps from synthia as _Priviledged Information_ during training to promote segmentation. Like DADA.|
| BDL | Bidirectional Learning for Domain Adaptation of Semantic Segmentation | 2019 | [link](https://arxiv.org/abs/1904.10620) |Simultaneous training of image translation and segmentation with _Selftraining_. Feedback from task to image tranlsation process. |
|---------| __Multimodal__ |
|BicycleGAN| Toward Multimodal Image-to-Image Translation | Nov 2017| [link](https://arxiv.org/abs/1711.11586)| Explicitly modeled multimodal domain-specific latent space. Style sampling possible. Conditional VAE-GAN combined with a latent regressor loss.|
|StarGAN| Unified Generative Adversarial Networks for Multi-Domain Image-to-Image Translation| Nov 2017|[link](https://arxiv.org/abs/1711.09020)|Simultaneous training on different datasets. Synthesizing facial expressions of celebrities, while using features learned from a dataset with different face expressions.|
|MUNIT| Multimodal Unsupervised Image-to-Image Translation | Apr 2018 | [link](https://arxiv.org/abs/1804.04732) | Based strongly on UNIT. Partially shared latent space assumption instead of fully shared latent space (UNIT). Here, only the content space is shared. Every domain has own style space. Sampling of styles possible.|

## Semantic Image Synthesis

Synhtesizing realistic images from a semantic layout.

| Abbr. | Paper Title | Publication | Link | Comment |
|-------|-------------|-------------|------|---------|
| pix2pix | Image-to-Image Translation with Conditional Adversarial Networks| nov 2016 | [link](https://arxiv.org/abs/1611.07004) |Real street scenery from segmentation mask. cGAN. no VAE. _Trained on paired data!_|
| pix2pixHD      | High-Resolution Image Synthesis and Semantic Manipulation with Conditional GANs | 2018 | [link](https://arxiv.org/abs/1711.11585) | Trained on paired data as well. Photo-realism through enhancer networks. Using border maps with layouts as extended input, a feature matching loss, and multi-scale discriminators. |
| SPADE      | Semantic Image Synthesis with Spatially-Adaptive Normalization | 2019 | [link](https://arxiv.org/abs/1903.07291) | Random vector as input instead of a semantic layout. The semantic segmentation is used to modulate the activations in normalization layers.|
|  | Learning to Predict Layout-to-image Conditional Convolutions for Semantic Image Synthesis | 2019 | [link](https://arxiv.org/abs/1910.06809) | A weight prediction network, with the layout as input condition, predicts the kernel weights of generator network. The generator gets noise as input and synthesizes the images. The discriminator conisders whether the images look real or fake and their semantic alignment.|
|  | Semantic Bottleneck Scene Generation | 2019 | [link](https://arxiv.org/abs/1911.11357) |They not only synthesize images, but also the semantic layouts. Using SPADE for image synthesis. |

## Latent Space Transformation

Domain adaptation in feature space

| Abbr. | Paper Title | Publication | Link | Comment |
|-------|-------------|-------------|------|---------|
|---------| __In combination with classification__ |
||Unsupervised Domain Adaptation by Backpropagation|2015|[link](https://arxiv.org/abs/1409.7495)| First approach to keep features domain-agnostic.|
|ADDA|Adversarial Discriminative Domain Adaptation| 2017| [link](https://arxiv.org/abs/1702.05464)| General 2-step approach to obtain equaling features for different domains (source domain determines feature space!)|
||Adversarial Feature Augmentation for Unsupervised Domain Adaptation|2018|[link](https://arxiv.org/abs/1711.08561)| Adversarial training in feature space (source domain determines feature space!)|
||Unsupervised Domain Adaptation with Similarity Learning|2018|[link](https://arxiv.org/abs/1711.08995)| Based on similarity to prototypes(source domain determines feature space!)|
|CADA|Attending to Discriminative Certainty for Domain Adaptation|2019|[link](https://arxiv.org/abs/1906.03502)| No entire-image-based domain adaptation, but to focus on regions that can be adapted better like foreground objects. Considers the probabilistic certainty estimate of various regions.|
|---------|__In combination with segmentation__|
||Conditional Generative Adversarial Network for Structured Domain Adaptation|2018|[link](https://ieeexplore.ieee.org/document/8578243)|Conditional generator translates feature maps, extracted from source images, into feature maps that are close to those of tagret images. No assumption of shared feature space: learning the residual between the feature maps from both domains|
||Domain adaptation for semantic segmentation via class-balanced self-traingin|2018|[]()|Introducing self-training for segmentation model.|
||Learning to Adapt Structured Output Space for Semantic Segmentation|2018|[link](https://arxiv.org/abs/1802.10349)|Adversarial learning on segmentation output (gap between domains is smaller there). Including multi-level domain adaptation in shared encoder.|
|DADA|Depth-Aware Domain Adaptation in Semantic Segmentation|2019|[link](https://arxiv.org/abs/1904.01886)|Unified depth-aware UDA framework using depth map as priviledged information in order to boost the segmentation task. Like SPIGAN.|
||Domain Adaptation for Structured Output via Discriminative Patch Representations|2019|[link](https://arxiv.org/abs/1901.05427)|Samples patches from source images and performs k-means clustering on patches. Aim is to get strcutured output by assigning patches to clusters|