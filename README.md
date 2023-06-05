# EPIC-KITCHENS-Audio-Based-Interaction-Recognition-Challenge-Fivewin-team
This is the code of the team Fivewin on the track, the code is abbreviated from the [baseline](https://github.com/epic-kitchens/epic-sounds-annotations/tree/main/src)
# 
**Environment**
If using conda, you can install the requirements with the following commands in you own conda environment. Rember to activate this environment with `conda activate epic-sounds`, or a similar name.

  * Python 3.9 `conda install python=3.9`
  * PyTorch 
    * CUDA 11.6: `conda install pytorch torchvision torchaudio pytorch-cuda=11.6 -c pytorch -c nvidia`
  * librosa `conda install -c conda-forge librosa`
  * wandb `conda install -c conda-forge wandb`
    * tensorboard `conda install -c conda-forge tensorboard`
  * h5py `conda install -c anaconda h5py`
  * fvcore `conda install -c fvcore -c iopath -c conda-forge fvcore`
    * iopath `conda install -c iopath iopath`
  * simplejson `conda install -c conda-forge simplejson`
  * psutil `conda install -c conda-forge psutil`
  * pandas `conda install pandas`
  * timm `conda install -c conda-forge timm`
# 
**Pretrained Models**
We just used [SlowFast pretrained weights](https://www.dropbox.com/s/339zsc6kz6c3wz9/SLOWFAST_EPIC_SOUNDS.pyth?dl=0), you can download it here
# 
**Fine-tune on EPIC-SOUNDS**
To fine-tune Slow-Fast on EPIC-Sounds, run:<br>
`python tools/run_net.py \<br>
--cfg configs/EPIC-Sounds/slowfast/SLOWFASTAUDIO_8x8_R50.yaml \<br>
NUM_GPUS num_gpus \<br>
OUTPUT_DIR /path/to/outpur_dir \<br>
EPICSOUNDS.AUDIO_DATA_FILE /path/to/EPIC_audio.hdf5 \<br>
EPICSOUNDS.ANNOTATIONS_DIR /path/to/annotations \<br>
TRAIN.CHECKPOINT_FILE_PATH /path/to/SLOWFAST_EPIC_SOUNDS.pyth \<br>
MODEL.FREEZE_BACKBONE True`

