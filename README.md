# Code Generator

A powerful tool that converts Python code to high-performance C++ code using state-of-the-art AI models. This project leverages OpenAI's GPT, Anthropic's Claude, and HuggingFace's CodeQwen models to automatically translate Python algorithms into optimized C++ implementations.

## Features

- **Multi-Model Support**: Choose from GPT-4, Claude 3.5 Sonnet, or CodeQwen for code translation
- **Performance Optimization**: Generates highly optimized C++ code with appropriate compiler flags
- **Cross-Platform**: Supports Windows (Visual Studio), Linux (GCC/Clang), and macOS (Clang with Apple M1 optimizations)
- **Interactive UI**: Gradio-based web interface for easy code conversion and testing
- **Real-time Comparison**: Execute both Python and C++ versions to compare performance and verify correctness
- **Streaming Output**: Real-time code generation with streaming responses from AI models
- **Sample Programs**: Pre-built examples including pi calculation and maximum subarray algorithms

## Requirements

### Python Dependencies

```bash
pip install openai anthropic google-generativeai python-dotenv gradio huggingface-hub transformers ipython jupyter
```

### System Requirements

- **Python 3.7+**
- **C++ Compiler**: One of the following:
  - **Windows**: Visual Studio 2019/2022 Build Tools
  - **Linux**: GCC (g++) or Clang++
  - **macOS**: Xcode Command Line Tools (Clang++)

### API Keys

You'll need API keys for the AI models you want to use:
- OpenAI API key (for GPT models)
- Anthropic API key (for Claude models)
- HuggingFace token (for CodeQwen models)

**Note**: For CodeQwen functionality, you'll need to set up HuggingFace endpoints. The notebook includes placeholder URLs that need to be replaced with your actual endpoint URLs.

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Sameeh07/Code_Generator.git
   cd Code_Generator
   ```

2. **Install Python dependencies**:
   ```bash
   pip install openai anthropic google-generativeai python-dotenv gradio huggingface-hub transformers ipython jupyter
   ```

3. **Set up environment variables**:
   Create a `.env` file in the project root:
   ```env
   OPENAI_API_KEY=your_openai_api_key_here
   ANTHROPIC_API_KEY=your_anthropic_api_key_here
   HF_TOKEN=your_huggingface_token_here
   ```

4. **Configure HuggingFace endpoints** (for CodeQwen):
   Update the endpoint URLs in the notebook:
   ```python
   CODE_QWEN_URL = "your_codeqwen_endpoint_url"
   CODE_GEMMA_URL = "your_codegemma_endpoint_url"  # Optional
   ```

5. **Install C++ compiler** (platform-specific):
   - **Windows**: Install Visual Studio Community or Build Tools
   - **Linux**: `sudo apt install g++` or `sudo apt install clang`
   - **macOS**: `xcode-select --install`

## Usage

### Interactive Jupyter Notebook

1. **Start Jupyter**:
   ```bash
   jupyter notebook
   ```

2. **Open the notebook**:
   Open `code gen.ipynb` in your browser

3. **Run the cells** to initialize the environment and start the Gradio interface

### Gradio Web Interface

The Gradio interface provides:
- **Python Code Input**: Paste or type your Python code
- **Model Selection**: Choose between GPT, Claude, or CodeQwen
- **Sample Programs**: Quick access to pre-built examples
- **Platform Detection**: Automatic detection of your system and available compilers
- **Real-time Conversion**: Stream the C++ code generation process
- **Execution**: Run both Python and C++ versions to compare results

### Programmatic Usage

```python
from your_module import optimize_gpt, optimize_claude, stream_code_qwen

# Python code to convert
python_code = """
def calculate_fibonacci(n):
    if n <= 1:
        return n
    return calculate_fibonacci(n-1) + calculate_fibonacci(n-2)

print(calculate_fibonacci(30))
"""

# Convert using GPT
optimize_gpt(python_code)

# Convert using Claude
optimize_claude(python_code)

# The optimized C++ code will be saved to 'optimized.cpp'
```

## Sample Programs

### 1. Pi Calculation
High-performance pi calculation using the Leibniz formula:
```python
def calculate(iterations, param1, param2):
    result = 1.0
    for i in range(1, iterations+1):
        j = i * param1 - param2
        result -= (1/j)
        j = i * param1 + param2
        result += (1/j)
    return result

result = calculate(100_000_000, 4, 1) * 4
```

### 2. Maximum Subarray Sum
Complex algorithm with random number generation:
```python
def max_subarray_sum(n, seed, min_val, max_val):
    # Uses Linear Congruential Generator for reproducible random numbers
    # Implements Kadane's algorithm for maximum subarray sum
    # Processes multiple iterations for statistical analysis
```

## Technical Details

### Supported AI Models

- **OpenAI GPT-4**: Latest GPT-4 model with excellent code generation capabilities
- **Anthropic Claude 3.5 Sonnet**: Advanced reasoning and code optimization
- **CodeQwen 1.5-7B**: Specialized code generation model from Alibaba


### Performance Features

- **Streaming**: Real-time code generation with immediate feedback
- **Memory Management**: Optimized for large-scale computations
- **Type Safety**: Automatic handling of integer overflow prevention
- **Platform Detection**: Automatic compiler and architecture detection



## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is open source. 




## Acknowledgments

- OpenAI for GPT models
- Anthropic for Claude models  
- HuggingFace for CodeQwen and model hosting
- Gradio for the interactive interface
