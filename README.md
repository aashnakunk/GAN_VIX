# GAN_VIX
Generating VIX values using different kinds of Generative Adversarial Networks.

This repo examines the application of Generative Adversarial Networks (GANs) to the generation of financial time series data, with a focus on the CBOE VIX Index. Traditional financial datasets often suffer from limitations such as insufficient size and complexity, which challenge the training of effective machine learning models. GANs, introduced by Goodfellow et al. in 2014, utilize a game theory framework involving two adversarially trained neural networks to generate data that mimics real distributions. Despite their success in domains such as image processing, their efficacy in financial applications remains less explored. This study compares several GAN architectures—LinGAN, ResNetGAN, Attention GAN, Vanilla GAN, CGAN, and WGAN in their ability to replicate the nuanced distribution and temporal properties of the VIX Index, known for its Gaussian nature interspersed with random spikes. Through rigorous statistical testing and visual evaluations, we assess the performance of these models, highlighting the potential of GANs as a tool for enhancing the robustness and diversity of financial datasets. This exploration contributes to the broader understanding of GAN capabilities in handling the unique challenges presented by financial time series data.

This is a very small dataset, i.e., it doesn't really have features other than data and the VIX value, which makes generating real data even harder. A distance based loss like Wasserstein loss, with the WGAN architecture seemed to be the best model for this particular dataset, and we further tuned its hyperparameters and explored options like training the discriminator more than the generator (5:1)  in order to make our WGAN model perform better. 

The best predictions were done by our Enhanced WGAN model and the real v/s generated data looked like this at the last epoch: 

<img width="691" alt="Screenshot 2024-05-21 at 10 55 18 AM" src="https://github.com/aashnakunk/GAN_VIX/assets/58456702/5b04af43-0962-4adf-95f3-8be9369bbec5">


This is a very decent prediction, especially for the limited two-column dataset we have. 

Visual inspection does well while working with GANs, but to compare models which gave close results, I did calculate the mean of the real data anad generated data at every epoch and compared the mean value at the last epoch for one model with the same value for another model to see which one predicts data better. For example, my Attention GAN and Enhanced WGAN model performed well, and there was no way to distinguish which one actually does better by just visual inspection. The conditional GAN produced a mean difference between real and fake data of 0.0289 and the enhanced WGAN produced a mean difference between real and fake data of 0.0001. Clearly, the enhanced WGAN predicted closer values overall! 

Feel free to let me know whether you think this metric was a good idea, whether it's appropriate, any discrepancies which can arise due to this,  and whether there's any better metric to compare model performance. 

Email: aashnakunk@gmail.com

# More details in the report in this repo 

