PyTorch implementation of 
[Efficiently Trainable Text-to-Speech System Based on Deep Convolutional Networks with Guided Attention](https://arxiv.org/abs/1710.08969)
based partially on the following projects:
* https://github.com/Kyubyong/dc_tts (audio pre processing)
* https://github.com/r9y9/deepvoice3_pytorch (data loader sampler)

## Online TTS Demo
The following notebooks are executable on [https://colab.research.google.com ](https://colab.research.google.com):
* [Mongolian Male Voice Demo](https://colab.research.google.com/github/tugstugi/pytorch-dc-tts/blob/master/notebooks/MongolianTTS.ipynb)
* [English Female Voice Demo (LJ-Speech)](https://colab.research.google.com/github/tugstugi/pytorch-dc-tts/blob/master/notebooks/EnglishTTS.ipynb)

For audio samples, visit the above notebook links.

## Training/Synthesizing English (LJ-Speech)
1. Download the dataset: `python dl_and_preprop_dataset.py --dataset=ljspeech`
   * see [LJ-Speech](https://keithito.com/LJ-Speech-Dataset/)
2. Train the Text2Mel model: `python train-text2mel.py --dataset=ljspeech`
3. Train the SSRN model: `python train-ssrn.py --dataset=ljspeech`
4. Synthesize sentences: `python synthesize.py --dataset=ljspeech`
   * The WAV files are saved in the `samples` folder.

## Training/Synthesizing Mongolian
1. Download the dataset: `python dl_and_preprop_dataset.py --dataset=mbspeech`
   * 5 hours audio from the [Mongolian Bible](https://www.bible.com/mn/versions/1590-2013-ariun-bibli-2013) used as the dataset.
2. Train the Text2Mel model: `python train-text2mel.py --dataset=mbspeech`
3. Train the SSRN model: `python train-ssrn.py --dataset=mbspeech`
4. Synthesize sentences: `python synthesize.py --dataset=mbspeech`
   * The WAV files are saved in the `samples` folder.