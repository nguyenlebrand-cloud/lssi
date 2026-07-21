brew install ollama          # hoặc tải ở ollama.com/download — cần ≥0.19 cho MLX runner
ollama pull qwen3:14b        # ⚠️ đối chiếu tag thật trên registry trước khi pull
launchctl setenv OLLAMA_HOST "0.0.0.0:11434"   # BẮT BUỘC, nếu không Windows gọi không tới
# restart Ollama sau lệnh trên
ipconfig getifaddr en0       # lấy IP Mac (không ra thì thử en1)
curl http://localhost:11434/api/tags           # tự test trên Mac
