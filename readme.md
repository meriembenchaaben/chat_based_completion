# Local LLaMA (70B) with vLLM OpenAI-Compatible Server

This README documents how to set up a Python environment, install dependencies, and run a local **vLLM** server that exposes an **OpenAI-compatible API** for GPTQ-quantized LLaMA models.

---

## 1) Create & activate a virtual environment

```bash
python3 -m venv ~/.venvs/llama
source ~/.venvs/llama/bin/activate
```

---

## 2) Install dependencies

### Option A — from `requirements.txt`
```bash
pip install -r requirements.txt
```

### Option B — install packages manually
```bash
python -m pip install -U pip wheel setuptools
python -m pip install -U transformers accelerate optimum
python -m pip install --no-build-isolation auto-gptq
python -m pip install -U openai
```

---

## 3) GPU environment variables (recommended)

```bash
# Use all 4 GPUs
export CUDA_VISIBLE_DEVICES=0,1,2,3

# Helps fragmentation (won't fix capacity issues, but good practice)
export PYTORCH_CUDA_ALLOC_CONF=expandable_segments:True
```

---

## 4) Run the vLLM OpenAI API server

### A) Serve LLaMA 3.3 70B GPTQ INT4
```bash
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
```

---

## Notes

- `--tensor-parallel-size 4` assumes **4 GPUs** are visible (see `CUDA_VISIBLE_DEVICES`).
- If you hit OOM issues, reduce:
  - `--max-model-len`
  - `--max-num-seqs`
  - `--gpu-memory-utilization`
- The server listens on: `http://127.0.0.1:8000`
