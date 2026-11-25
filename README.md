# LLM_Study

### 安裝 llama.cpp
+ 官方網站: https://llama.app/
+ 官方Github: https://github.com/ggml-org/llama.cpp
+ 版本: https://github.com/ggml-org/llama.cpp/releases
+ 目標模型: https://huggingface.co/unsloth/Inkling-2-Mini-GGUF/blob/main/Inkling-2-Mini-UD-IQ1_M.gguf

### 安裝 LM Studio Bionic
+ 官方網站: https://lmstudio.ai/
+ 版本: Bionic-1.1.7-7-x64
+ 安裝後無法運行的話，要安裝VC套件:
  + 微軟介紹頁面: https://learn.microsoft.com/zh-tw/cpp/windows/latest-supported-vc-redist?view=msvc-170#latest-supported-redistributable-version
  + 選擇項目: https://aka.ms/vc14/vc_redist.x64.exe
 
### 安裝 LM Studio
+ 官方網站: https://lmstudio.ai/
+ 版本: LM-Studio-0.4.25-1-x64.exe

### 測試
+ curl -X GET http://100.80.0.5:1234/v1/models -H "Content-Type: application/json" -H "Authorization: Bearer sk-lm-ymGJE2gr:lScQk8zKVLydJf1QuKw7"


### WorkBuddy
+ 官方網站(國際版): https://www.workbuddy.ai/
+ 輔助工具: https://github.com/Vanszs/VansRouter
+ 虛擬機練習:
  + 來自opencode系列VM，轉存為: Win10_VansRouter_VM1
  + 變更電腦名稱:「設定」＞「系統」＞「關於」＞「重新命名此電腦（進階）」，電腦名稱改為「VansRouterVM1」。
    + 設定變更電腦名稱後重新啟動電腦。
  + 有必要的話，重灌opencode。
  + 安裝: https://nodejs.org/zh-tw/download
    + node-v26.13.1-x64.msi。
  + 安裝: https://github.com/Vanszs/VansRouter
    ```
    請使用繁體中文回答。
    請幫我安裝https://github.com/Vanszs/VansRouter
    使用npm安裝。
    我要允許他監聽所有的IP:  0.0.0.0。並且要放行防火牆。
    並使用預設的密碼123456。
    啟用原生工具的Auto-start功能。
    ```
    ```
    創建一個全部允許的API KEY並且Require API key啟用。
    並且製作jsonc讓指定專案下我能夠使用workbuddy和opencode來源的模型。
    ```
+ opencode設定檔
```
{
  // ─────────────────────────────────────────────────────────────
  //  OpenCode 專案設定（僅作用於專案中）
  //  走本機 VansRouter 的 OpenAI 相容 API，後端接 CodeBuddy（cbai/*）
  // ─────────────────────────────────────────────────────────────
  "$schema": "https://opencode.ai/config.json",

  // 預設模型：vansrouter/<下面 models 的 key>
  "model": "vansrouter/deepseek-v4.1-flash",

  "providers": {
    "vansrouter": {
      "name": "VansRouter (CodeBuddy)",
      "package": "@opencode/ai/providers/openai-compatible",
      "settings": {
        "baseURL": "http://127.0.0.1:20128/v1",
        // VansRouter 儀表板建立的 API Key（明碼）
        "apiKey": "sk-184ecf8808216032-13yyi5-8e74a27b"
      },

      "models": {
        "deepseek-v4.1-flash": {
          "modelID": "cbai/deepseek-v4.1-flash",
          "name": "CodeBuddy · DeepSeek V4.1 Flash",
          "capabilities": { "tools": true, "input": ["text", "image"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 1000000, "output": 128000 }
        },
        "deepseek-v4-pro": {
          "modelID": "cbai/deepseek-v4-pro",
          "name": "CodeBuddy · DeepSeek V4 Pro",
          "capabilities": { "tools": true, "input": ["text"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 1000000, "output": 384000 }
        },
        "deepseek-v3-2-volc": {
          "modelID": "cbai/deepseek-v3-2-volc",
          "name": "CodeBuddy · DeepSeek V3.2 (Volc)",
          "capabilities": { "tools": true, "input": ["text"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 128000, "output": 64000 }
        },
        "glm-5.2": {
          "modelID": "cbai/glm-5.2",
          "name": "CodeBuddy · GLM 5.2",
          "capabilities": { "tools": true, "input": ["text"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 1000000, "output": 131072 }
        },
        "glm-5.1": {
          "modelID": "cbai/glm-5.1",
          "name": "CodeBuddy · GLM 5.1",
          "capabilities": { "tools": true, "input": ["text"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 200000, "output": 128000 }
        },
        "glm-5.0": {
          "modelID": "cbai/glm-5.0",
          "name": "CodeBuddy · GLM 5.0",
          "capabilities": { "tools": true, "input": ["text"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 200000, "output": 128000 }
        },
        "glm-5.0-turbo": {
          "modelID": "cbai/glm-5.0-turbo",
          "name": "CodeBuddy · GLM 5.0 Turbo",
          "capabilities": { "tools": true, "input": ["text"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 200000, "output": 128000 }
        },
        "glm-5v-turbo": {
          "modelID": "cbai/glm-5v-turbo",
          "name": "CodeBuddy · GLM 5V Turbo（視覺）",
          "capabilities": { "tools": true, "input": ["text", "image"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 200000, "output": 128000 }
        },
        "glm-4.7": {
          "modelID": "cbai/glm-4.7",
          "name": "CodeBuddy · GLM 4.7",
          "capabilities": { "tools": true, "input": ["text"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 200000, "output": 128000 }
        },
        "minimax-m3": {
          "modelID": "cbai/minimax-m3",
          "name": "CodeBuddy · MiniMax M3（視覺）",
          "capabilities": { "tools": true, "input": ["text", "image"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 1048576, "output": 512000 }
        },
        "minimax-m2.7": {
          "modelID": "cbai/minimax-m2.7",
          "name": "CodeBuddy · MiniMax M2.7",
          "capabilities": { "tools": true, "input": ["text"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 204800, "output": 131072 }
        },
        "kimi-k2.7": {
          "modelID": "cbai/kimi-k2.7",
          "name": "CodeBuddy · Kimi K2.7（視覺）",
          "capabilities": { "tools": true, "input": ["text", "image"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 262144, "output": 262144 }
        },
        "kimi-k2.6": {
          "modelID": "cbai/kimi-k2.6",
          "name": "CodeBuddy · Kimi K2.6（視覺）",
          "capabilities": { "tools": true, "input": ["text", "image"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 262144, "output": 262144 }
        },
        "kimi-k2.5": {
          "modelID": "cbai/kimi-k2.5",
          "name": "CodeBuddy · Kimi K2.5（視覺）",
          "capabilities": { "tools": true, "input": ["text", "image"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 262144, "output": 262144 }
        },
        "hy3-preview": {
          "modelID": "cbai/hy3-preview",
          "name": "CodeBuddy · Hunyuan 3 Preview",
          "capabilities": { "tools": true, "input": ["text"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 262144, "output": 262144 }
        },

        // ── 以下為 VansRouter 內建免驗證來源（noAuth），不是 CodeBuddy ──
        // oc/* = provider id "opencode"（OpenCode Zen 免費層，7 個模型）
        // 注意：免費層有每日額度，用完會回 429 FreeUsageLimitError

        "oc-deepseek-v4.1-flash-free": {
          "modelID": "oc/deepseek-v4.1-flash-free",
          "name": "OpenCode · DeepSeek V4.1 Flash (Free)",
          "capabilities": { "tools": true, "input": ["text", "image"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 200000, "output": 32000 }
        },
        "oc-glm-5.3-flash-free": {
          "modelID": "oc/glm-5.3-flash-free",
          "name": "OpenCode · GLM 5.3 Flash (Free)",
          "capabilities": { "tools": true, "input": ["text", "image"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 200000, "output": 32000 }
        },
        "oc-mimo-v2.6-flash-free": {
          "modelID": "oc/mimo-v2.6-flash-free",
          "name": "OpenCode · MiMo v2.6 Flash (Free)",
          "capabilities": { "tools": true, "input": ["text", "image"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 200000, "output": 32000 }
        },
        "oc-nemotron-3.5-super-vl-free": {
          "modelID": "oc/nemotron-3.5-super-vl-free",
          "name": "OpenCode · Nemotron 3.5 Super VL (Free)",
          "capabilities": { "tools": true, "input": ["text", "image"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 1048576, "output": 131072 }
        },
        "oc-nemotron-3.5-lightning-free": {
          "modelID": "oc/nemotron-3.5-lightning-free",
          "name": "OpenCode · Nemotron 3.5 Lightning (Free)",
          "capabilities": { "tools": true, "input": ["text"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 262144, "output": 262144 }
        },
        "oc-minimax-m3.1-flash-free": {
          "modelID": "oc/minimax-m3.1-flash-free",
          "name": "OpenCode · MiniMax M3.1 Flash (Free)",
          "capabilities": { "tools": true, "input": ["text", "image"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 1000000, "output": 512000 }
        },
        "oc-beam-free": {
          "modelID": "oc/beam-free",
          "name": "OpenCode · Beam (Free)",
          "capabilities": { "tools": true, "input": ["text"], "output": ["text"], "reasoning": { "supported": true } },
          "limit": { "context": 1048576, "output": 131072 }
        },

        // mmf/* = provider id "mimo-free"（小米 MiMo 免費來源）
        // 目前實測上游回 502（MiMo bootstrap failed: 404），先列著但不建議當主力
        "mmf-mimo-auto": {
          "modelID": "mmf/mimo-auto",
          "name": "MiMo · MiMo Auto (Free)",
          "capabilities": { "tools": true, "input": ["text"], "output": ["text"] }
        }
      }
    }
  }
}

```
