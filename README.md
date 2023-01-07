# GAN_LFW

Implementation of a Generative Adversarial Network (GAN) with a convolutional generator and discriminator. The provided model was effectively trained on a preprocessed LFW dataset (36x36, centered) on 1 GPU.

<p align="center">
  <img src="https://user-images.githubusercontent.com/42875258/143950484-9a8dbbb9-8807-436d-b639-7bc0b54cadd4.gif" width="525">
</p>

This personal project taught me a lot code-wise, and it opened my eyes to certain aspects of machine learning. I sincerely hope that those who will find time to read this README will find something interesting here themselves, or at least they can enjoy some peculiar images of my creation.

## Quality of generated images

Even though this GAN works with low-resolution images, it is still incredible how well this model can extract semantic information from the dataset. Generated images are diverse and demonstrate complex properties including face symmetry, facial hair, occasionally glasses or even hats. Not to mention, the variety of facial expressions is just striking.

<p align="center">
  <img src="https://user-images.githubusercontent.com/42875258/143947116-ea1f6bde-145e-47fe-844d-8b8c64a88380.png" width="175">
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://user-images.githubusercontent.com/42875258/143947122-8401c65b-ab14-4139-80e5-b6193e0d0888.png" width="175">
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://user-images.githubusercontent.com/42875258/143947125-fd302735-ac9a-425e-8374-13aa294f8b34.png" width="175">
</p>

It was a revelation to me that GANs have a natural predisposition to providing diverse outputs. This is so because if a generator were to focus on creating images of a particular type, a discriminator would lower predictions for images of this type, punishing the generator's "dullness". That is why the generator's output space seems to resemble the training dataset.

## Witnessing internal "adversarial" attack (GAN's collapse)

Sooner or later, the discriminator might become overpowered by its generator. That means that fake images satisfy the discriminator's conditions better than real ones. Then, if the discriminator is too slow to retrain, it will start making progressively bad decisions. This situation might ultimately lead to the collapse of the model.

<p align="center">
  <img src="https://user-images.githubusercontent.com/42875258/143992399-fb33e836-dae5-4da9-9fdb-0f4ed05b0c7a.gif" width="600"><br>
  <img src="https://user-images.githubusercontent.com/42875258/143959911-a0f2e9df-71b7-4108-9a61-b6def7e57086.png" width="300">
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://user-images.githubusercontent.com/42875258/143983246-6bd347b8-4dea-4ccc-b42f-4d4f8bf5d5dc.png" width="300">
</p>

The discriminator may rank fake images higher than real ones, but that says little about their quality. The figures above demonstrate how the quality of the generator's output might degrade, as it happens during the GAN's collapse. 


## Importance of Batch normalization

The importance of including batch normalization layers is hard to overstate. Working with random noise, they help immensely for the signal to travel throughout the net.

<p align="center">
  <img src="https://user-images.githubusercontent.com/42875258/143985635-c7e9d4ba-ca59-41e8-a615-133abdc78b57.png" width="200">
  <img src="https://user-images.githubusercontent.com/42875258/143985750-bcdd995e-ff6c-4bc5-91a5-57212a070e3f.png" width="200">
  <img src="https://user-images.githubusercontent.com/42875258/143985769-ad1e3100-fa67-47db-8c5d-eb8705686f9d.png" width="200">
</p>

As a curiosity, I  have included the most disturbing images obtained without implementing batch normalization.
