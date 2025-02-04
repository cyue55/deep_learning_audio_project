# Deep Learning Audio Project for the DTU course 02456 

## Overview
This project aims to finetune the descript-audio-codec for speech enhancement and noise removal. 

## Components

- **Data Preparation**: Custom dataloaders and datasets manage voice and noise data, and creating noisy speech data. 
- **Model Architecture**: Utilizes `dac` (Descript Audio Codec), a high-fidelity general neural audio codec, with both generator and discriminator networks for adversarial training.
- **HifiPlusPlus**: The discriminators from HPP can be used to improve the quality of the generated audio.
- **Loss Functions**: A diverse set of losses, including L1, Mel-Spectrogram, SI-SDR, and GAN losses, are used to capture various aspects of audio reconstruction quality.
- **Training Routine**: A training loop with loss weighting, noise addition, and gradient clipping to create stable learning.
- **Evaluation**: The model's output is periodically saved for quality inspection, and performance metrics are tracked during training.

## Usage

Training is is done using the train script with config for folders, parameters etc. in the config file.

- **training_audiotools.py**: Advanced script utilizing custom audio loaders, various loss functions, and a detailed training loop with audio sample saving.
- **simple_training_SI-SDR.py**: A streamlined training script focusing on optimizing the Scale-Invariant Signal-to-Distortion Ratio metric.

### Training

To start the training process, run the desired script with:

```sh
python3 train.py
```

Adjust hyperparameters such as learning rates, batch sizes, folder setup and epochs within the config file.

## Output

Models, logs, and audio samples are saved in the `./output/` directory, allowing for incremental evaluation of the audio processing quality.

See [Wandb for training logs](https://wandb.ai/thorhojhus/Audio-project)

---

Please refer to the individual scripts for detailed parameter settings and training customizations.
