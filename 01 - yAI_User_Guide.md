# yAI User Guide

Welcome to yAI! This guide will help you get started with creating custom AI assistants for your team.

---

## What is yAI?

yAI is a platform that lets you create personalized AI assistants with unique personalities, knowledge, and behaviors. Whether you need a marketing strategist, customer support agent, or creative writing partner, you can build an AI that fits your exact needs.

**Key Features:**
- Create unlimited custom AI personas
- Chat with your AIs in real-time
- Attach documents from Google Drive or Notion for context
- Share AIs across your team (organization accounts)
- Connect your AIs to external apps via API (yFlows)
- Group chat with multiple AIs and team members

---

## Getting Started

### Step 1: Sign Up

1. Visit the yAI platform
2. Click **Sign In** in the top right corner
3. Create an account using your email or Google sign-in
4. Verify your email if prompted

### Step 2: Create Your First AI

1. Click the **+ Create AI** button
2. Fill in the AI's details:
   - **Name**: Give your AI a memorable name (e.g., "Nova", "Atlas", "Maya")
   - **Identity**: Describe who your AI is and how it should behave
   - **Role**: Select a template or create a custom role
   - **Colors**: Choose theme colors for your AI's chat interface

3. Click **Save** to create your AI

**Tips for Writing an Identity:**
- Be specific about expertise: "You are an expert in social media marketing with 10 years of experience"
- Define personality: "You are friendly, encouraging, and use simple language"
- Set boundaries: "You focus only on marketing topics and politely redirect off-topic questions"

### Step 3: Start Chatting

1. Click on your saved AI card
2. The chat window will open
3. Type your message and press Enter or click Send
4. Your AI will respond based on its personality and identity

---

## Features Guide

### Conversations

**Starting a New Chat:**
- Each conversation is automatically saved
- Click **New Chat** to start a fresh conversation
- Use the sidebar to view your conversation history

**Conversation Sidebar:**
- Shows all your past conversations with this AI
- Click any conversation to continue where you left off
- Delete old conversations you no longer need

**Auto-Naming:**
- After a few messages, yAI automatically gives your conversation a descriptive title
- This helps you find conversations later

---

### Attaching Documents

You can give your AI context from your documents to get more relevant answers.

#### Google Drive

1. Click the **attachment** icon in the chat input
2. Select **Google Drive**
3. If not connected, click **Connect Google Drive**
4. Complete the Google sign-in process
5. Select your document from the picker
6. The document content will be attached to your message

**Supported Files:**
- Google Docs, Sheets, Slides
- PDFs
- Word documents (.docx)
- Text files

#### Notion

1. Click the **attachment** icon in the chat input
2. Select **Notion**
3. If not connected, click **Connect Notion**
4. Select which pages to share during the authorization
5. Browse your pages and click one to attach it

**Note:** Only pages you share during Notion setup will be visible. To add more pages, disconnect and reconnect Notion, selecting additional pages.

---

### Managing Your Integrations

Access your integration settings from the menu:

1. Click the **menu** icon in the top right
2. Select **Integrations**
3. View connected services
4. Connect or disconnect services as needed

---

### Organizations (Team Accounts)

Organizations let you share AI assistants with your team.

#### Creating an Organization

1. Click your profile icon
2. Select **Create Organization**
3. Enter your organization name
4. You become the Admin automatically

#### Inviting Team Members

*Requires an active subscription or beta access*

1. Switch to your organization account
2. Click the **Members** button in the menu
3. Enter the email address of your team member
4. They'll receive an invitation email

**Seat Management:**
- Your subscription includes a base seat (you)
- Purchase additional seats for team members ($100/month each)
- View available seats in the Members modal

#### Roles

| Role | Can Do |
|------|--------|
| Admin | Create/edit/delete AIs, invite members, manage billing |
| Member | Create AIs, use all team AIs, chat |

---

### yFlows (API Access)

yFlows lets you connect your AI to external applications, websites, and automation platforms.

#### What Can You Do with yFlows?

- Embed your AI in your website
- Connect to Zapier for automations
- Build custom chatbots
- Integrate with Slack, Discord, or other platforms
- Create mobile app AI features

#### Generating an API Key

1. Click the **menu** icon
2. Select **yFlows**
3. Choose which AI to connect
4. Give your key a name (e.g., "Website Bot")
5. Click **Generate API Key**
6. **Copy your key immediately** - it won't be shown again!

#### Managing Keys

- View all your keys in the yFlows modal
- Keys show the AI name, creation date, and a partial key preview
- Click **Revoke** to permanently disable a key

*See the [yFlows API Guide](./YFLOWS_API_GUIDE.md) for technical integration details.*

---

### Group Chat

Chat with multiple AIs and team members in the same conversation.

#### Adding AIs to a Conversation

1. Open a conversation
2. Click the **+** button to add participants
3. Select additional AIs to join
4. Each AI responds based on its unique personality

#### Using @ Mentions

In group conversations, use @ mentions to direct questions to specific AIs:

- `@Nova what do you think?` - Only Nova responds
- `@Nova and @Atlas, compare your approaches` - Both respond
- No @ mention in a multi-AI chat = No AI responds (lets humans chat)

---

## Billing

### Subscription Plans

| Plan | Price | Includes |
|------|-------|----------|
| Base Subscription | $500/month | 1 admin seat, unlimited AIs, yFlows access |
| Additional Seats | $100/month each | Add team members |

### Managing Your Subscription

1. Click the **Members** button (org accounts only)
2. View your current subscription status
3. Click **Manage Billing** to access Stripe portal
4. Update payment method, view invoices, or cancel

### Beta Access

Beta organizations have full access without payment during the trial period.

---

## Tips & Best Practices

### Creating Effective AIs

1. **Be Specific**: The more detail in the identity, the better the responses
2. **Set Tone**: Define how formal or casual your AI should be
3. **Give Examples**: Include sample responses in the identity
4. **Define Scope**: Specify what topics the AI should focus on

### Getting Better Responses

1. **Provide Context**: Attach relevant documents before asking questions
2. **Be Clear**: Ask specific questions rather than vague ones
3. **Iterate**: If the response isn't quite right, ask for clarification
4. **Use History**: Reference earlier parts of the conversation

### Organization Best Practices

1. **Create Role-Based AIs**: Make specialized AIs for different tasks
2. **Document Identities**: Keep a record of what each AI is designed for
3. **Share Knowledge**: Team members can learn from each other's AI configurations
4. **Manage Keys**: Revoke API keys when team members leave

---

## Troubleshooting

### Can't See My AIs

- Check if you're in the right account (personal vs organization)
- Try refreshing the page
- Ensure you're signed in

### Document Won't Attach

- Check that the integration is connected
- For Notion, ensure the page was shared during setup
- For Google Drive, ensure you have read access to the file
- Try disconnecting and reconnecting the integration

### AI Not Responding as Expected

- Review the AI's identity in Edit mode
- Check if you're in the right conversation context
- Try starting a new conversation

### Can't Generate API Keys

- Ensure you have an active subscription or beta access
- Organization members need the organization to have a subscription
- Try refreshing the page

### Invitation Not Received

- Check spam/junk folder
- Verify the email address is correct
- Ensure you have available seats



## Quick Reference

| Action | How To |
|--------|--------|
| Create AI | Click + Create AI button |
| Start Chat | Click on AI card |
| New Conversation | Click New Chat in sidebar |
| Attach Document | Click attachment icon |
| Add Team Member | Members > Invite |
| Generate API Key | Menu > yFlows |
| Switch Accounts | Click profile dropdown |
| Manage Billing | Members > Manage Billing |

---

*Last Updated: February 2026*
