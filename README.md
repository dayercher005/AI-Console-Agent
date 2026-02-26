# AI Console Agent with Golang

Run your own AI Console Agent with your own Anthropic API Key and Golang.

## AI Agent Definition

Definition: An autonomous software system that uses artificial intelligence to achieve specific goals by perceiving its environment, reasoning, planning, and taking actions (usually without human intervention). Unlike passive models, agents use tools, possess memory and can break down complex tasks into manageable steps.

## Key Features of an AI Agent:

* Memory: Able to maintain context from past interactions to improve future performance, compared to LLMS that have short-term memory
* Tool Usage: They can interact with external software, APIs, and databases to perform actions.
* Autonomy: Agents operate independently to complete tasks, rather than just providing answers.

---

## Setup & Installation

### Prerequisites
* Go. You can install it <a target="_blank" href="https://go.dev/doc/install">here</a>
* Anthropic API Key, and set it as an environment variable, `ANTHROPIC_API_KEY`. 

### 1. Clone the repository
```git
git clone git@github.com:dayercher005/AI-Console-Agent.git
```

### 2. Enable Dependency Tracking for Go
```bash
go mod tidy
```

### 3. Export API Key into Console:
```bash
export ANTHROPIC_API_KEY="Your API Key Details here"
```

### 3. Run it on the console: 
```bash
go run main.go
```
---

## Sample Response (using Messages API of Claude API)

Request:
```shell
curl https://api.anthropic.com/v1/messages \
  --header "x-api-key: $ANTHROPIC_API_KEY" \
  --header "anthropic-version: 2023-06-01" \
  --header "content-type: application/json" \
  --data '{
    "model": "claude-opus-4-6",
    "max_tokens": 1024,
    "messages": [
      {"role": "user", "content": "Hello, Claude"}
    ]
  }'
```


Response:
```json
{
  "id": "msg_01XFDUDYJgAACzvnptvVoYEL",
  "type": "message",
  "role": "assistant",
  "content": [
    {
      "type": "text",
      "text": "Hello! How can I assist you today?"
    }
  ],
  "model": "claude-opus-4-6",
  "stop_reason": "end_turn",
  "usage": {
    "input_tokens": 12,
    "output_tokens": 8
  }
}
```
---

### Acknowledgements

View the Anthropic Golang API Library <a href="https://github.com/anthropics/anthropic-sdk-go?tab=readme-ov-file">here</a>
