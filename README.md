# Lyre
## Setup
You need `conda` to set up the environments. There are two of them. One (`whisper.yml`) is to help create datasets, the other (`tacotron2.yml`) is for training and inference of the Tacotron2 and WaveGlow models.

You also need to initialize and update the submodules.
```
git submodule init
git submodule update
```
## Config Settings
### Tacotron2
Modify `hparams.py` under `tacotron2/` for training and inference.

Change the following key-value pairs to something like:
```
iters_per_checkpoint=500,
fp16_run=True,
training_files='./lyre/dataset/obama-full/train_tacotron.txt',
validation_files='./lyre/dataset/obama-full/valid_tacotron.txt',
learning_rate=1e-4,
batch_size=48,
```

### WaveGlow
Modify `config.json` under `waveglow/` for training.

Change the following key-value pairs to something like:
```
"output_directory": "./lyre/waveglow_checkpoints",
"training_files": "./lyre/dataset/test/train_waveglow.txt",
```