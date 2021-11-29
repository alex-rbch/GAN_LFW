# GAN_LFW

Implementation of a Generative Adversarial Network (GAN) with convolutional generator and discriminator. The provided model was trained on the preprocessed LFW dataset (36x36, centered) for 2 hours on 1 GPU.

<p align="center">
  <img src="https://user-images.githubusercontent.com/42875258/143950484-9a8dbbb9-8807-436d-b639-7bc0b54cadd4.gif" width="700">
</p>

This is my personal project that taught me a lot code-wise and definitively opened my eyes on certain aspects of machine learning. I sincerely hope that those who will find time to read this README will find something interesting for them here as well or at least they can enjoy some peculiar images of my creation.

## Quality of generated images

Even though this GAN works with low-resolution images, it is still incredible how well this small model can differentiate semantic information from the dataset. Generated images are diverse and demonstrate complex properties, such as face symmetry, facial hair, occasionally glasses and hats. The variety of facial expressions is just striking.

<p align="center">
  <img src="https://user-images.githubusercontent.com/42875258/143947116-ea1f6bde-145e-47fe-844d-8b8c64a88380.png" width="250" style="margin-right: 200px;">
  $~~~$
  <img src="https://user-images.githubusercontent.com/42875258/143947122-8401c65b-ab14-4139-80e5-b6193e0d0888.png" width="250">
  <img src="https://user-images.githubusercontent.com/42875258/143947125-fd302735-ac9a-425e-8374-13aa294f8b34.png" width="250">
</p>

It was a revelation to me that GANs have a natural predisposition to providing diverse outputs. This is so because if a generator were to focus on creating images of a paricular type, a discriminator would lower predictions for images of this type, punishing generator's uncreativity. That is why generator tends to map to the output space analogous to the training dataset.  
