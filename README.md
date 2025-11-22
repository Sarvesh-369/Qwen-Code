# Qwen Code (Vision Support Fork)

This is a modified version of **Qwen Code** that adds robust vision model support for non-interactive workflows and extends compatibility to self-hosted/OpenAI-compatible endpoints.

## 🚀 Key Changes

### 1. Vision Support in Non-Interactive Mode

- **Fixed**: You can now attach images directly in the command line using the `@path/to/image.jpg` syntax.
- **Auto-Switching**: The CLI automatically detects images and switches to a vision-capable model (defaulting to a one-time switch) to process the request.

**Example:**

```bash
qwen --prompt "Describe this image @data/images/1.jpg"
```

### 2. Extended Authentication Support

- **Universal Compatibility**: The vision model auto-switching logic is no longer restricted to Qwen OAuth.
- **Self-Hosted / vLLM**: Works seamlessly with self-hosted models (e.g., vLLM serving Qwen-VL) or any OpenAI-compatible endpoint, provided the model supports vision inputs.

## 📦 Installation

To install this version from source:

1. **Clone the repository:**

   ```bash
   git clone https://github.com/Sarvesh-369/Qwen-Code.git
   cd Qwen-Code
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Build the packages:**

   ```bash
   npm run build:packages
   ```

4. **Link the CLI globally:**

   ```bash
   cd packages/cli
   npm link
   ```

5. **Verify installation:**
   ```bash
   qwen --version
   ```

## 🛠️ Usage

### Basic Usage

```bash
qwen
```

### Vision Task (Non-Interactive)

```bash
qwen -y -p "Describe this image @path/to/image.jpg"
```

### Configuration

You can configure the vision switching behavior in `.qwen/settings.json` or via flags:

```bash
# Switch once per query (default)
qwen --vlm-switch-mode once

# Switch for entire session
qwen --vlm-switch-mode session
```

---

_For original documentation, please refer to the [original repository](https://github.com/QwenLM/qwen-code)._
