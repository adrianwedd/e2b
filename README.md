<h1 align="center">
  <img width="200" src="docs-assets/logoname-black.svg#gh-light-mode-only" alt="e2b">
  <img width="200" src="docs-assets/logoname-white.svg#gh-dark-mode-only" alt="e2b">
</h1>

<p align="center">Open-source IDE powered by AI agents that do the work for you</p>

<h4 align="center">
  <a href="https://e2b.dev">Website</a> |
  <a href="https://discord.gg/U7KEcGErtQ">Discord</a> |
  <a href="https://twitter.com/e2b_dev">Twitter</a>
</h4>

<h4 align="center">
  <a href="https://discord.gg/U7KEcGErtQ">
    <img src="https://img.shields.io/badge/chat-on%20Discord-blue" alt="Discord community server" />
  </a>
  <a href="https://twitter.com/e2b_dev">
    <img src="https://img.shields.io/twitter/follow/infisical?label=Follow" alt="e2b Twitter" />
  </a>
</h4>

![e2b-editor](docs-assets/e2b.png)
*Example of AI agent building Stripe checkout. Left - technical specification written by human. Right - steps that the AI agent took and tools that it used to build the server route required by the specification.*

[e2b](https://e2b.dev) or etob (*english2bits*) is an open-source virtual software developer. These virtual developers are powered by AI agents and can use tools.

The developer writes a short documentation or a technical spec in plain English and then lets the AI agent do the actual work. The AI agents have access to tools like writing to a file, running code, running commands, installing dependencies, deploying, etc. 

Agents operate in our own secure sandboxed cloud environments that's powered by [Firecracker](https://github.com/firecracker-microvm/firecracker/). This way, you for example describe what a server route should do and the agent codes it for you. Like [this example](https://twitter.com/mlejva/status/1641072535163875330) of an AI agent coding Stripe customer checkout based on a technical spec.

e2b currently supports building only REST servers in Node.js. Specifically using the [Express](https://expressjs.com/) framework. We'll support more languages and frameworks with time. The goal for e2b is to eventually be able to handle any use-case.

# 🚀 Get started
We're working on the cloud-hosted version. In the meantime, the fastest way try out e2b is to run it locally via Docker.

## 🐳 Start e2b with Docker
You will need:
- [OpenAI API key](https://platform.openai.com/account/api-keys) (support for more and custom models coming soon)
- Docker
- Node.js *16+*
- Free ports 3000 (Next.js app), 54321 (Supabase API Gateway), 54322 (Supabase Database)

To start e2b run:
```
npm start
```

Then open page on [http://localhost:3000](http://localhost:3000).

`npm start` starts local Supabase in the background - to stop it you have to run `npm run stop`.

## 💻 Development setup
For developing with hot reloading and contributing to the project you may want to run the app locally without Docker (`npm start` command).

[Follow these steps](DEVELOPMENT_SETUP.md) to set it up.

# Features
## 🛠 Bring your own X
While e2b will offer the "batteries-included" solution, our goal is to let users:
- **BYOM** - Bring Your Own Model
- **BYOP** - Bring Your Own Prompt
- **BYOT** - Bring Your Own Tools

We think the AI-powered IDE for the future should be open-sourced and allow anybody to bring their models, customize the prompts, and develop custom tools for the agents. But we also plan to offer a cloud version with some features behind subscription though.

## 🤖 Supported models and model hosting providers
- [x] [OpenAI](https://openai.com/)
  - [x] GPT-4
  - [x] GTP-3.5
- [ ] [Replicate](https://replicate.com/) 🚧
- [ ] [HuggingFace](https://huggingface.co/) 🚧
- [ ] [Anthropic](https://anthropic.com/) 🚧
  - [ ] Claude v1.3
  - [ ] Claude Instant v1

### **Model or model hosting provider you like isn't supported?**

👉 Please open the ["New model request" issue](https://github.com/e2b-dev/e2b/issues/new?assignees=&labels=new+model+request&template=new-model-request.md&title=) 👈

👉 Or open a PR and [start contributing](./CONTRIBUTING.md#🤖-adding-a-new-model-provider) 👈

## 👀 Early demos
- [AI Agent using coding tools](https://twitter.com/mlejva/status/1636103084802822151)
- [Build your custom "Just-In-Time" UI](https://twitter.com/mlejva/status/1641151421830529042)
- [Agent coded a full Stripe customer checkout by following a technical spec provided by user](https://twitter.com/mlejva/status/1641072535163875330)

# ℹ️ Community & Support
- [Discord](https://discord.gg/U7KEcGErtQ) - live discussion and support
- [GitHub issues](https://github.com/e2b-dev/e2b/issues) - for reporting bugs
- [Twitter](https://twitter.com/e2b_dev) - to stay up to date

# 🤝 Contributing
We welcome any contributions! If you want to contribute to the project check out the [contibution guide](CONTRIBUTING.md) and join our [Discord](https://discord.gg/dSBY3ms2Qr).

# 📆 Roadmap
1. Make sure people can run e2b locally without issues and the DX is smooth.
2. Add support for more models.
    - Let users request new models. Later create a system that will let users use any model.
3. Improve model's understanding of the context based on the instructions
4. Support for more tools
5. Improve the dashboard UI
6. Let users edit prompt
7. Let users customize tools and build custom workflows for the agent
8. Release cloud version
