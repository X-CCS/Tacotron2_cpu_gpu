# Tacotron2_cpu_gpu Inference modified based on: 

https://github.com/NVIDIA/DeepLearningExamples/tree/master/PyTorch/SpeechSynthesis/Tacotron2

Use PyTorch 20.03-py3 NGC container or newer 
bash scripts/docker/build.sh

bash scripts/docker/interactive.sh


Tacotron2 and WaveGlow checkpoints for inference can be downloaded from NGC, and place in the current directory:

https://ngc.nvidia.com/catalog/models/nvidia:tacotron2pyt_fp16/files?version=3

https://ngc.nvidia.com/catalog/models/nvidia:waveglow256pyt_fp16/files?version=2


GPU run: 

python inference.py --tacotron2 tacotron2_1032590_6000_amp --waveglow waveglow_1076430_14000_amp --wn-channels 256 -o output/ -i phrases/phrase.txt

GPU benchmarking:

bash test_infer.sh

bash run_latency_tests.sh (different batch size, precision)


CPU run: 

export CUDA_VISIBLE_DEVICES=

python inference.py --tacotron2 tacotron2_1032590_6000_amp --waveglow waveglow_1076430_14000_amp --wn-channels 256 --cpu-run -o output/ -i phrases/phrase.txt

CPU benchmarking:

bash test_infer.sh --cpu-run

bash run_latency_tests_cpu.sh (different batch size)
