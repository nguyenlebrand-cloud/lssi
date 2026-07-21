brew install ollama          # hoặc tải ở ollama.com/download — cần ≥0.19 cho MLX runner
ollama pull qwen3:14b        # ⚠️ đối chiếu tag thật trên registry trước khi pull
launchctl setenv OLLAMA_HOST "0.0.0.0:11434"   # BẮT BUỘC, nếu không Windows gọi không tới
# restart Ollama sau lệnh trên
ipconfig getifaddr en0       # lấy IP Mac (không ra thì thử en1)
curl http://localhost:11434/api/tags           # tự test trên Mac
192.168.1.67
lsof -nP -iTCP:11434 -sTCP:LISTEN
COMMAND PID       USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
ollama  980 nhanvien01    4u  IPv4 0x1fd06b5d1928d3f3      0t0  TCP 127.0.0.1:11434 (LISTEN)
# 1. Quit app Ollama trên thanh menu TRƯỚC (nếu đang chạy bản app) — quan trọng,
#    vì app sẽ tự hồi sinh server với env cũ, pkill không đủ.
pkill ollama

# 2. Chạy thẳng, ép binding:
OLLAMA_HOST=0.0.0.0:11434 ollama serve
