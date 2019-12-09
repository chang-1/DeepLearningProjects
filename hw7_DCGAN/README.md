Deep Convolutional Generative Adversarial Networks (DCGAN)

based on this paper(in the dir): https://arxiv.org/pdf/1511.06434.pdf

/
- download.py
- preprocess.py
- assignment.py   | generator model
                  | discriminator model
                  | main func
- data/celebA   (images for training)
- output        (fake images generated by G model)
- checkpoints    -| ...

## Dependency
This project is run on GCP CS147 virtual environment. Besides, these:
* tqdm
* tensorflow_gan
* tensorflow_hub
* imageio
* requests
packages are also required.

## Preprocess
Run 'python download.py' to download data. A dir 'data' is generated. 
Run 'cd data; tar -xvzf celebA.tar' to unzip tha data. There're nearly 2 million celeb face images.

## Train
Run 'python assignment.py' to start train again. 
Checkpoints will be stored in /checkpoints every 500 iterartions during the train. 

## Test
Run 'python assignment.py --mode=test' to start test mode. 
Latest checkpoints will be loaded and a batch of images will be generated by G model and stored in /output. 
Hopefully they can be recognized as almost human faces in Picasso style! 

## Conclusion
It takes about 2 hours on GCP K80 GPU to train the model for 10 epoch.
My average FID per batch is around 170 at the end of train. 