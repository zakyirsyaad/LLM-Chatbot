# LLM Chatbot

![LLM Chatbot](https://icp.ninja/examples/_attachments/llm_chatbot.png)

The LLM Chatbot example demonstrates how an ICP smart contract can be used to interact with a large language model (LLM) to generate text. The user can input a prompt, and the smart contract will use the LLM to generate a response.
The response is then returned to the user, and the user can submit some follow-up prompts to continue the conversation.

This application's logic is written in [Rust](https://internetcomputer.org/docs/building-apps/developer-tools/cdks/rust/intro-to-rust).

## What is ICP Ninja?

ICP Ninja is a web-based integrated development environment (IDE) for the Internet Computer. It allows you to write code and deploy applications directly from your web browser in a temporary, sandbox-like environment.

For users who may already be familiar with the Internet Computer or who would rather use more **advanced tooling** such as command-line development tools, please refer to the [ICP developer documentation](https://internetcomputer.org/docs/building-apps/getting-started/install) to learn more.

Projects deployed to ICP from ICP Ninja are available on the mainnet for 20 minutes at a time. After 20 minutes, the project must be redeployed.

To deploy your project for long-term, production use such that it persists longer than 20 minutes without needing to be redeployed, you must migrate the files off of ICP Ninja and deploy them to the mainnet via `dfx` in a command-line environment.

## Project structure

The `/backend` folder contains the Rust smart contract:

- `Cargo.toml`, which defines the crate that will form the backend
- `lib.rs`, which contains the actual smart contract, and exports its interface

The `/frontend` folder contains web assets for the application's user interface. The user interface is written using the React framework.

## Continue building locally

To migrate your ICP Ninja project off of the web browser and develop it locally, follow these steps.

### 1. Download your project from ICP Ninja using the 'Download files' button on the upper left corner under the pink ninja star icon.

### 2. Setting up Ollama

To be able to test the agent locally, you'll need a server for processing the agent's prompts. For that, we'll use `ollama`, which is a tool that can download and serve LLMs.
See the documentation on the [Ollama website](https://ollama.com/) to install it. Once it's installed, run:

```
ollama serve
# Expected to start listening on port 11434
```

The above command will start the Ollama server, so that it can process requests by the agent. Additionally, and in a separate window, run the following command to download the LLM that will be used by the agent:

```
ollama run llama3.1:8b
```

The above command will download an 8B parameter model, which is around 4GiB. Once the command executes and the model is loaded, you can terminate it. You won't need to do this step again.

### 3. Open the `BUILD.md` file for further instructions.
