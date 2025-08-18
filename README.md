# RAG Playground

This repository provides a playground environment for experimenting with Retrieval-Augmented Generation (RAG) techniques.

## Prerequisites

Before getting started, ensure you have the following installed on your system:

- [uv](https://astral.sh/uv) (recommended) or Python 3.9+
- [Ollama](https://ollama.com) (for local LLMs)
- [Jupyter](https://jupyter.org) (for running notebooks)

## Setup

### 1. Install `uv` (Recommended)

On **Linux/macOS**:

```sh
curl -LsSf https://astral.sh/uv/install.sh | sh
```

On **Windows** (PowerShell):

```sh
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

For other platforms or details, see the [official `uv` installation guide](https://docs.astral.sh/uv/getting-started/installation).

### 2. Install Dependencies

With `uv`:

```sh
uv sync
```

This will create a virtual environment in the `.venv` folder and install all dependencies there.

### 3. Alternative: Using `requirements.txt`

If you prefer not to use `uv`, you can set up a virtual environment manually:

```sh
python3 -m venv .venv
source .venv/bin/activate  # On Windows use `.venv\Scripts\activate`
pip install -r requirements.txt
```

### 4. Install Ollama

Download and install Ollama from the [official website](https://ollama.com/download).

On **Linux/macOS**, you can also install it via:

```sh
curl -fsSL https://ollama.com/install.sh | sh
```

> On macOS, you may need to start Ollama manually:
>
> ```sh
> ollama serve
> ```

### 5. Pull Required Models

Once Ollama is running, pull the necessary models:

```sh
ollama pull llama3.2:1b
ollama pull snowflake-arctic-embed2:latest
```

### 6. Download Required Data

The `data/` folder is initially empty.

You need to manually download the **u-blox F9 HPG 1.32 Interface Description** PDF from [u-blox's website](https://content.u-blox.com/sites/default/files/documents/u-blox-F9-HPG-1.32_InterfaceDescription_UBX-22008968.pdf) and place it in the `data/` folder.

Expected structure:

```
data/
└── InterfaceDescription.pdf
```

## Running the Notebook

The recommended way to run the notebook is with **VS Code** and the [Jupyter extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter).

Alternatively, you can use the `jupyter` CLI:

Install Jupyter with `uv`:

```sh
uv add jupyter
```

Or with `pip`:

```sh
pip install jupyter
```

Start the notebook server:

```sh
jupyter notebook
```

Then open `rag.ipynb` and run the cells.
