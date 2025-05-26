This program was created to build a choir with Voice Conversion AI

for now it excuted only for mac m series

To start this program, 

```
git clone https://github.com/single-bungle/audience-choir.git 
cd audience-choir
python3 -m venv venv  
source venv/bin/activate 
pip install -r requirements.txt
```

GUI GUIDE
1. upload targets audio file(singers voices)
   1) you can find samples in "/local-dataset"
   2) you can upload many audio files
   3) check boxes to activate
2. upload source(song)
3. set parameters - recommend default setting
   -  source is the path to the speech file to convert to reference voice
   - target is the path to the speech file as voice reference
   - output is the path to the output directory
   - diffusion-steps is the number of diffusion steps to use, default is 25, use 30-50 for best quality, use 4-10 for fastest inference
   - length-adjust is the length adjustment factor, default is 1.0, set <1.0 for speed-up speech, >1.0 for slow-down speech
   - inference-cfg-rate has subtle difference in the output, default is 0.7
   - f0-condition is the flag to condition the pitch of the output to the pitch of the source audio, default is False, set to True for singing voice conversion
   - auto-f0-adjust is the flag to auto adjust source pitch to target pitch level, default is False, normally not used in singing voice conversion
   - semi-tone-shift is the pitch shift in semitones for singing voice conversion, default is 0
   - checkpoint is the path to the model checkpoint if you have trained or fine-tuned your own model, leave to blank to    auto-download default model from huggingface.(seed-uvit-whisper-small-wavenet if f0-condition is False else seed-uvit-whisper-base)
   - config is the path to the model config if you have trained or fine-tuned your own model, leave to blank to auto-download default config from huggingface
   - fp16 is the flag to use float16 inference, default is True

4. once you excute program, they automatically install voice conversion models pre-trained parameters(usually it tooks few minutes)
5. when the conversion over - you can apply spatial audio effects(drag and drop to desinated position and click 'apply spatial audio - usually it took less then a second)
6. then you can save outputs
