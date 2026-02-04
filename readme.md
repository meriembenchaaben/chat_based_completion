Run this:


python3 -m venv ~/.venvs/llama
source ~/.venvs/llama/bin/activate

pip install -r requirements.txt


or .. 
python -m pip install -U pip wheel setuptools
python -m pip install -U transformers accelerate optimum
python -m pip install --no-build-isolation auto-gptq
python -m pip install -U openai



# Use all 4 GPUs
export CUDA_VISIBLE_DEVICES=0,1,2,3

# Helps fragmentation (won't fix capacity issues, but good practice)
export PYTORCH_CUDA_ALLOC_CONF=expandable_segments:True

python -m vllm.entrypoints.openai.api_server \
  --model /Tmp/benchaam/huggingface/Meta-Llama-3.1-70B-Instruct-GPTQ-INT4 \
  --served-model-name llama31-70b \
  --tensor-parallel-size 4 \
  --host 127.0.0.1 --port 8000

  python -m vllm.entrypoints.openai.api_server \
  --model /Tmp/benchaam/huggingface/Meta-Llama-3.1-70B-Instruct-GPTQ-INT4 \
  --served-model-name llama31-70b \
  --tensor-parallel-size 4 \
  --max-model-len 1024 \
  --enforce-eager \
  --gpu-memory-utilization 0.85 \
  --host 127.0.0.1 --port 8000


  python -m vllm.entrypoints.openai.api_server \
  --model /Tmp/benchaam/huggingface/clowman-Llama-3.3-70B-Instruct-GPTQ-Int4 \
  --served-model-name llama3.3-70b \
  --quantization gptq \
  --dtype float16 \
  --tensor-parallel-size 4 \
  --max-model-len 1024 \
  --gpu-memory-utilization 0.80 \
  --max-num-seqs 32 \
  --enforce-eager \
  --host 127.0.0.1 --port 8000
