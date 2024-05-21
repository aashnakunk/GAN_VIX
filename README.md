# GAN_VIX
Generating VIX values using different kinds of Generative Adversarial Networks.

This repo examines the application of Generative Adversarial Networks (GANs) to the generation of financial time series data, with a focus on the CBOE VIX Index. Traditional financial datasets often suffer from limitations such as insufficient size and complexity, which challenge the training of effective machine learning models. GANs, introduced by Goodfellow et al. in 2014, utilize a game theory framework involving two adversarially trained neural networks to generate data that mimics real distributions. Despite their success in domains such as image processing, their efficacy in financial applications remains less explored. This study compares several GAN architectures—LinGAN, ResNetGAN, Attention GAN, Vanilla GAN, CGAN, and WGAN in their ability to replicate the nuanced distribution and temporal properties of the VIX Index, known for its Gaussian nature interspersed with random spikes. Through rigorous statistical testing and visual evaluations, we assess the performance of these models, highlighting the potential of GANs as a tool for enhancing the robustness and diversity of financial datasets. This exploration contributes to the broader understanding of GAN capabilities in handling the unique challenges presented by financial time series data.

This is a very small dataset, i.e., it doesn't really have features other than data and the VIX value, which makes generating real data even harder. A distance based loss like Wasserstein loss, with the WGAN architecture seemed to be the best model for this particular dataset, and we further tuned its hyperparameters and explored options like training the discriminator more than the generator in order to make our WGAN model perform better. 

The best predictions were done by our Enhanced WGAN model and the real v/s generated data looked like this at the last epoch: 

<img width="678" alt="Screenshot 2024-05-20 at 11 23 32 PM" src="https://github.com/aashnakunk/GAN_VIX/assets/58456702/de9483d5-2deb-4103-b6da-9b125b9d5b3b">

This is a very decent prediction, especially for the limited two-column dataset we have. 

For a deeper understanding, I've provided a report in this repo which you could read.

Any questions: aashnakunk@gmail.com
