# Tacotron2_cpu_gpu Inference

bash scripts/docker/interactive.sh

GPU run: python inference.py --tacotron2 tacotron2_1032590_6000_amp --waveglow waveglow_1076430_14000_amp --wn-channels 256 -o output/ -i phrases/phrase.txt

bash test_infer.sh

bash run_latency_tests.sh



CPU run: 

export CUDA_VISIBLE_DEVICES=
python inference.py --tacotron2 tacotron2_1032590_6000_amp --waveglow waveglow_1076430_14000_amp --wn-channels 256 --cpu_run -o output/ -i phrases/phrase.txt

bash test_infer.sh --cpu-run

bash run_latency_tests_cpu.sh
