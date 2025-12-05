## Bot Config YAML Reference

### Identity
| Field | Description |
|-------|-------------|
| `name` | Display name for the bot |
| `innerName` | Internal name used in message formatting |

### Model Settings
| Field | Description |
|-------|-------------|
| `mode` | `prefill` (completion-style) or `chat` (chat API) |
| `continuation_model` | Model identifier (e.g., `claude-3-5-sonnet-20241022`) |
| `temperature` | Randomness (0.0-2.0, higher = more creative) |
| `max_tokens` | Max output tokens per response |
| `top_p` | Nucleus sampling (0.0-1.0) |
| `presence_penalty` | Penalize repeated topics (0.0-2.0) |
| `frequency_penalty` | Penalize repeated tokens (0.0-2.0) |

### Thinking/Reasoning
| Field | Description |
|-------|-------------|
| `prefill_thinking` | Prefill with `<thinking>` tag for reasoning |
| `debug_thinking` | Show thinking as `.`-prefixed debug message |
| `preserve_thinking_context` | Keep thinking traces in context history |

### Context Window
| Field | Description |
|-------|-------------|
| `recency_window_messages` | Max messages to include |
| `recency_window_characters` | Max characters to include |
| `hard_max_characters` | Absolute character limit (default 500k) |
| `rolling_threshold` | Messages before context rolls/truncates |
| `recent_participant_count` | Recent participants for stop sequences |
| `authorized_roles` | Roles allowed for `.history` commands (empty = all) |

### Images
| Field | Description |
|-------|-------------|
| `include_images` | Include image attachments in context |
| `max_images` | Max images to include |

### Tools
| Field | Description |
|-------|-------------|
| `tools_enabled` | Enable tool/function calling |
| `tool_output_visible` | Show tool calls in Discord |
| `max_tool_depth` | Max consecutive tool call iterations |
| `tool_plugins` | Built-in plugins to enable (e.g., `['config']`) |
| `mcp_servers` | List of MCP server configs (name, command, args, env) |

### Behavior
| Field | Description |
|-------|-------------|
| `stop_sequences` | Additional sequences to stop generation |
| `message_delimiter` | Appended to each message (e.g., `</s>` for base models) |
| `system_prompt` | System prompt text |
| `system_prompt_file` | Path to system prompt file |
| `reply_on_random` | 1/N chance to reply randomly (500 = 0.2%) |
| `reply_on_name` | Reply when name mentioned |
| `max_queued_replies` | Max queued replies before dropping |

### Retries & Limits
| Field | Description |
|-------|-------------|
| `llm_retries` | LLM API retry attempts |
| `discord_backoff_max` | Max Discord API backoff (ms) |
| `max_bot_reply_chain_depth` | Max consecutive bot messages (prevents loops) |

--

Note: May drift out of date over time. This was produced on 2025 Dec 5. Regenerate with a prompt like:

> please could you prepare a short and precise markdown document explaining the exact config yaml fields and what they do (to be pasted into discord)?
