# Proposal.Biz MCP for AI Agentic Chat Bot

**Proposal.Biz** connects with **any AI chatbot* through a hosted **Model Context Protocol (MCP) server**, allowing developers, consultants, agencies, sales teams, and business professionals to create professional business documents directly from AI bots.

With the Proposal.Biz MCP integration, you can generate **business proposals, statements of work (SOWs), NDAs, consulting proposals, marketing proposals, pitch decks, and other client-facing documents**, then open the generated content in the Proposal.Biz builder for further editing and refinement.

**Website:** proposal.biz
**MCP endpoint:** `https://app.proposal.biz/api/mcp`

## What is Proposal.Biz?

Proposal.Biz is an AI-powered proposal and business document creation platform designed for professionals and organizations that need to create polished, client-ready business documents faster.

It is particularly useful for:

* Software development and IT services companies
* Digital and marketing agencies
* Consulting firms and independent consultants
* Sales and business development teams
* Freelancers and professional service providers
* Startups and founders
* Creative and design agencies
* Businesses creating proposals, SOWs, agreements, and presentations

The MCP integration enables these users to start document creation from their development or AI-assisted workflow without manually switching between applications.

## Connect Proposal.Biz to AI bot

Proposal.Biz provides a hosted MCP server that can be connected to AI bot through MCP/connector settings.

### MCP Configuration

Add the following configuration to your MCP/connector configuration:

```json
{
  "mcpServers": {
    "proposal-biz": {
      "type": "http",
      "url": "https://app.proposal.biz/api/mcp"
    }
  }
}
```

### Authentication

On first use, AI bot should initiate the Proposal.Biz sign-in and authorization flow.

Sign in to your Proposal.Biz account at:

`https://app.proposal.biz`

Approve the requested access to complete the connection.

**OAuth is the recommended authentication method, and no API key is required when using OAuth.**

## Connect Using a Proposal.Biz API Key

Proposal.Biz also supports personal API keys. API keys use the `pbz_` prefix.

Create a personal API key from your Proposal.Biz account's API key settings and configure MCP with the key as a bearer token:

```json
{
  "mcpServers": {
    "proposal-biz": {
      "type": "http",
      "url": "https://app.proposal.biz/api/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_PBZ_API_KEY"
      }
    }
  }
}
```

**Security:** Keep API keys private. Never commit a real Proposal.Biz API key to a Git repository, configuration shared with others, or public code.

## Available Proposal.Biz MCP Tools

The Proposal.Biz MCP server currently provides tools for interacting with the Proposal.Biz account and creating business documents.

### `create_proposal`

Creates a new Proposal.Biz document from a title and Markdown content.

Supported output types include:

* `document` — business proposals, SOWs, NDAs, consulting documents, and other documents
* `presentation` — pitch decks and business presentations
* `webpage` — proposal and business content intended for web presentation

The default output type is `document`.

Creating a document requires the `write:proposals` permission.

### `get_user_profile`

Returns information about the connected Proposal.Biz user, including:

* Name
* Email
* Active organization
* User role

### `get_profile`

Returns the stable Proposal.Biz account profile associated with the connected client.

## Example Prompts for Agentic AI Chatbot

Once Proposal.Biz is connected to MCP client, users can ask AI chatbot to create professional business documents.

### Software Development Proposal

> Create a detailed proposal for redesigning and developing a company's customer portal. Include project objectives, understanding of requirements, recommended approach, scope of work, deliverables, technology considerations, project phases, timeline, team structure, assumptions, client responsibilities, and estimated investment.

### Digital Marketing Proposal

> Create a marketing proposal for a growing D2C brand looking to improve its digital presence. Include the business context, marketing objectives, recommended strategy, key initiatives, deliverables, implementation timeline, measurement framework, and estimated investment.

### Consulting Proposal

> Create a consulting proposal for a mid-sized company looking to improve its sales process. Include the current business challenges, engagement objectives, recommended approach, key activities, deliverables, timeline, client responsibilities, assumptions, and professional fees.

### Architecture and Interior Design Proposal

> Create a proposal for designing a modern commercial office space. Cover the project understanding, design objectives, design approach, scope of work, project phases, timeline, team, deliverables, assumptions, client responsibilities, and professional fees.

### Branding Proposal

> Create a branding proposal for a new technology company. Include brand strategy, positioning, visual identity, messaging, creative process, key deliverables, project phases, timeline, team structure, assumptions, and investment.

## Recommended Workflow

For best results, users should:

1. **Describe the business requirement** and intended audience.
2. **Provide relevant project information**, such as scope, objectives, deliverables, timeline, budget, and client requirements.
3. Ask AI chatbot to **draft the complete content** before creating the Proposal.Biz document.
4. **Review the generated draft** for accuracy, completeness, assumptions, and client-specific details.
5. Ask the Proposal.Biz MCP server to create the selected output format.
6. Use the returned **Proposal.Biz link** to open the result in the Proposal.Biz builder.
7. Continue editing, formatting, and refining the document in Proposal.Biz before sharing it with the client.

This review step is important: AI-generated business documents should be checked for factual accuracy, pricing, scope, timelines, assumptions, and other client-specific information before being sent externally.

## Why Use Proposal.Biz with AI chatbot?

The integration combines **Chatbot's AI-assisted development environment** with Proposal.Biz's business document creation workflow.

It is useful when a developer, agency, consultant, or professional services team needs to move from a technical or business requirement to a **structured, professional proposal or business document** without manually recreating the content in another application.

Typical use cases include:

* Software development proposals
* Website and mobile app development proposals
* SaaS implementation proposals
* IT consulting proposals
* Digital marketing proposals
* Branding and creative proposals
* Sales proposals
* Consulting engagements
* Statements of Work (SOWs)
* Business presentations
* Pitch decks
* Client-facing webpages
* Other professional business documents

## Key Benefits

**AI-assisted document creation**
Turn project requirements and business context into structured proposal content.

**Cursor workflow integration**
Create business documents without leaving the Cursor workflow.

**Multiple output formats**
Generate documents, presentations, or webpages depending on the use case.

**Editable Proposal.Biz output**
Open the generated result in the Proposal.Biz builder and continue refining the content.

**Secure authentication options**
Connect through OAuth or use a personal Proposal.Biz API key when appropriate.

**Useful for multiple business functions**
The integration supports workflows across sales, consulting, software development, marketing, design, and professional services.

## Important Security Note

If using API-key authentication, treat the `pbz_` API key as a secret credential. Store it securely using appropriate environment variables or secret-management mechanisms and do not expose it in source code, public repositories, documentation, screenshots, or chat messages.

## Resources

**Proposal.Biz:** `https://proposal.biz`
**Proposal.Biz App:** `https://app.proposal.biz`
**Proposal.Biz MCP endpoint:** `https://app.proposal.biz/api/mcp`
**Listed in the [Claude Market MCP directory]** `https://www.claudemarket.ai/mcp`

## License

MIT
