ollama pull qwen2.5-coder:7b               snippets ,c 13B ya codea mejor

- set OLLAMA_NUM_THREADS=16                usa todos los cores
- set OLLAMA_NUM_PARALLEL=1                evita multiples modelos en la RAM
- set OLLAMA_MAX_LOADED_MODELS=1

- set num_ctx 4096                          contexto , tambien podes subirlo a 8k pero consume mucha mas ram
