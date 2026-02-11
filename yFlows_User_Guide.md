# yFlows User Guide

Connect your yAI personas to websites, apps, and automation tools.

---

## What is yFlows?

yFlows lets you use your custom AI personas anywhere - not just in the yAI chat interface. Generate an API key, and your AI's personality travels with it to any platform you integrate.

**Use Cases:**
- Add a chatbot to your website
- Build custom mobile app AI features
- Create Zapier automations
- Connect to Slack, Discord, or Teams
- Build voice assistants
- Power email auto-responders

---

## Getting Started

### Step 1: Generate Your API Key

1. Open yAI and sign in
2. Click the **Menu** icon (top right)
3. Select **yFlows**
4. Choose your AI from the dropdown
5. Give your key a name (e.g., "Website Bot", "Zapier Integration")
6. Click **Generate API Key**

**Important:** Copy your key immediately! It's only shown once. Store it somewhere safe.

### Step 2: Test Your Key

Try this in your terminal or command prompt:

```bash
curl -X POST https://elysia-api.ngrok.io/api/public/v1/chat/completions \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"model": "elysia", "messages": [{"role": "user", "content": "Hello!"}]}'
```

You should get a response from your AI with its unique personality!

---

## How It Works

When you generate a key for an AI, that AI's personality is automatically included. You don't need to set up the persona again - just send messages and your AI responds in character.

**What travels with your key:**
- Your AI's name and identity
- Its communication style
- Any special instructions you defined

---

## Making API Calls

### Basic Request

Send a POST request to:
```
https://elysia-api.ngrok.io/api/public/v1/chat/completions
```

**Headers:**
```
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json
```

**Body:**
```json
{
  "model": "elysia",
  "messages": [
    {"role": "user", "content": "Your message here"}
  ]
}
```

### Response

```json
{
  "choices": [
    {
      "message": {
        "role": "assistant",
        "content": "Your AI's response here"
      }
    }
  ]
}
```

---

## Code Examples

### Python

```python
import requests

API_KEY = "your-api-key"

response = requests.post(
    "https://elysia-api.ngrok.io/api/public/v1/chat/completions",
    headers={
        "Authorization": f"Bearer {API_KEY}",
        "Content-Type": "application/json"
    },
    json={
        "model": "elysia",
        "messages": [
            {"role": "user", "content": "Hello!"}
        ]
    }
)

print(response.json()["choices"][0]["message"]["content"])
```

### JavaScript

```javascript
const response = await fetch('https://elysia-api.ngrok.io/api/public/v1/chat/completions', {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer your-api-key',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    model: 'elysia',
    messages: [
      { role: 'user', content: 'Hello!' }
    ]
  })
});

const data = await response.json();
console.log(data.choices[0].message.content);
```

### Using OpenAI Libraries

yFlows works with existing OpenAI SDKs - just change the base URL:

**Python (OpenAI SDK):**
```python
from openai import OpenAI

client = OpenAI(
    api_key="your-yflows-key",
    base_url="https://elysia-api.ngrok.io/api/public/v1"
)

response = client.chat.completions.create(
    model="elysia",
    messages=[{"role": "user", "content": "Hello!"}]
)
```

**JavaScript (OpenAI SDK):**
```javascript
import OpenAI from 'openai';

const client = new OpenAI({
  apiKey: 'your-yflows-key',
  baseURL: 'https://elysia-api.ngrok.io/api/public/v1'
});

const response = await client.chat.completions.create({
  model: 'elysia',
  messages: [{ role: 'user', content: 'Hello!' }]
});
```

---

## Conversations with Memory

To maintain conversation context, include previous messages:

```json
{
  "model": "elysia",
  "messages": [
    {"role": "user", "content": "My name is Sarah"},
    {"role": "assistant", "content": "Nice to meet you, Sarah!"},
    {"role": "user", "content": "What's my name?"}
  ]
}
```

The AI will remember: "Your name is Sarah!"

**Tip:** Keep the last 10-20 messages for best performance.

---

## Real-Time Streaming

For chat interfaces, enable streaming to show responses as they're generated:

```json
{
  "model": "elysia",
  "messages": [{"role": "user", "content": "Tell me a story"}],
  "stream": true
}
```

Responses arrive piece by piece, creating a typing effect.

---

## Request Options

| Option | Description | Default |
|--------|-------------|---------|
| `model` | AI model to use (`elysia` recommended) | Required |
| `messages` | Array of conversation messages | Required |
| `temperature` | Creativity level (0 = focused, 1 = creative) | 0.7 |
| `max_tokens` | Maximum response length | 1000 |
| `stream` | Enable real-time streaming | false |

---

## Integration Ideas

### Website Chatbot

Add a chat widget to your website that uses your AI persona:

```html
<script>
let conversation = [];

async function sendMessage(userMessage) {
  conversation.push({ role: 'user', content: userMessage });

  const response = await fetch('https://elysia-api.ngrok.io/api/public/v1/chat/completions', {
    method: 'POST',
    headers: {
      'Authorization': 'Bearer YOUR_API_KEY',
      'Content-Type': 'application/json'
    },
    body: JSON.stringify({
      model: 'elysia',
      messages: conversation
    })
  });

  const data = await response.json();
  const aiMessage = data.choices[0].message.content;

  conversation.push({ role: 'assistant', content: aiMessage });
  return aiMessage;
}
</script>
```

**Security Note:** For production websites, route API calls through your backend server to protect your API key.

### Zapier

1. Create a new Zap
2. Add **Webhooks by Zapier** > **Custom Request**
3. Set **Method** to POST
4. Set **URL** to `https://elysia-api.ngrok.io/api/public/v1/chat/completions`
5. Add headers:
   - `Authorization: Bearer your-api-key`
   - `Content-Type: application/json`
6. Set body:
   ```json
   {"model": "elysia", "messages": [{"role": "user", "content": "{{trigger_data}}"}]}
   ```

### Slack / Discord Bots

Create a bot that:
1. Listens for messages
2. Sends them to yFlows API
3. Posts the AI response back to the channel

Many bot frameworks support custom webhooks - just point them to the yFlows API.

---

## Managing Your Keys

### Viewing Keys

1. Go to **Menu** > **yFlows**
2. See all your active keys with:
   - Key name
   - Connected AI
   - Creation date
   - Partial key preview

### Revoking Keys

If a key is compromised or no longer needed:

1. Go to **Menu** > **yFlows**
2. Find the key in the list
3. Click **Revoke**

The key stops working immediately. Generate a new one if needed.

### Best Practices

- **Create separate keys** for each integration (website, Zapier, etc.)
- **Name keys descriptively** so you remember what they're for
- **Revoke unused keys** to minimize risk
- **Never share keys publicly** or commit them to code repositories
- **Rotate keys periodically** for sensitive applications

---

## Troubleshooting

### "Invalid API key" Error

- Double-check you copied the full key
- Ensure there are no extra spaces
- Verify the key hasn't been revoked

### "Subscription required" Error

- Your subscription may have expired
- Check your billing status in yAI
- Generate a new key after renewing

### AI Not Responding as Expected

- The API uses the AI's saved personality
- Edit your AI in yAI to change its behavior
- Generate a new key after making changes

### Slow Responses

- Consider using streaming for real-time UX
- Reduce `max_tokens` for shorter responses
- Check your internet connection

---

## FAQ

**Q: Do I need to set up my AI's personality in the API call?**

No! Your AI's personality is automatically included when you generate a key. Just send messages.

**Q: Can I use the same key for multiple integrations?**

Yes, but we recommend separate keys for each integration. This way you can revoke one without affecting others.

**Q: What happens if I update my AI's personality?**

Changes take effect immediately for new conversations. For the updated personality to apply to API calls, generate a new key.

**Q: Is there a rate limit?**

We have reasonable limits to ensure fair usage. Most applications won't hit them. If you need higher limits, contact us.

**Q: Can I use yFlows without a subscription?**

yFlows requires an active subscription or beta access.

**Q: Is my API key secure?**

Keys are encrypted and stored securely. Never expose your key in client-side code or public repositories.

---

## Need Help?

- **Support:** support@yg3.ai
- **Documentation:** Check the docs folder for more guides

---

*Last Updated: February 2026*
