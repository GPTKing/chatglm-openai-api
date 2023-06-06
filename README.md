# chatglm-openai-api

Provide OpenAI style API for  ChatGLM-6B and Chinese Embeddings Model


## 注意事项

- 模型托管在 huggingface 上，需要良好的国际互联网访问体验。
- 默认运行在 GPU + CUDA 上。


## 高级功能


## 本地运行（ngrok 隧道，测试用）

> 注： ngrok 隧道在未付费的时候无法使用自定义域名，只能使用动态域名，仅用来演示  
> ngrok 的 token 和 subdomain，请在 config.toml 中配置

```bash
# 首先初始化虚拟环境
python3 -m venv .venv
source .venv/bin/activate

# 安装依赖
pip install -r requirements.txt

运行后，访问显示的 ngrok 隧道地址，即可使用 API，默认输出 `{"hello": "world"}`，该 API 和 OpenAI API 一致。

```bash

curl https://<your domain>/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $CHATGLM_API_KEY" \
  -d '{
    "model": "gpt-3.5-turbo",
    "messages": [{"role": "user", "content": "Hello!"}]
  }'
```



## 常见客户端配置


