# OllamaToGGUF
Convert a downloaded Ollama model back into its GGUF equivalent format.

## Author
Matthew O'Brien - mattjamo
https://github.com/mattjamo

## Overview

`OllamaToGGUF.py` is a Python script designed to convert models from Ollama's split format into a single GGUF (GPT General Unified Format) file. This script reads model manifests and combines the model layers stored in blob files into a unified GGUF file.

## Features

- **Manifest Parsing**: Reads and parses JSON manifest files to gather model configuration and layer information.
- **Blob File Handling**: Combines multiple blob files into a single GGUF file based on the manifest.
- **User Interaction**: Provides a simple command-line interface to select and convert models.

## Requirements

- Python 3.6 or higher, validated using python 3.11.9
- Access to Ollama model files (manifests and blobs) stored in the default Ollama directory (`~/.ollama/models/`).

## Setup

1. **Clone the Repository** (if not already done):
   ```bash
   git clone https://github.com/mattjamo/OllamaToGGUF.git
   cd OllamaToGGUF
   ```

## Usage

1. **Run the Script**:
   ```bash
   python OllamaToGGUF.py
   ```

2. **Select a Model**:
   The script will list available Ollama models to convert. Enter the number corresponding to the model you wish to convert.

3. **Conversion Process**:
   The script will read the selected model's manifest, combine the blob files, and save the resulting GGUF file in the `Output` directory.

4. **Exit**:
   Enter `0` to exit the script.

## Directory Structure

- `~/.ollama/models/manifests/registry.ollama.ai/`: Directory containing model manifest files.
- `~/.ollama/models/blobs/`: Directory containing model blob files.
- `Output/`: Directory where the converted GGUF files will be saved.

## Example

```bash or command prompt
$ python OllamaToGGUF.py

Ollama To GGUF

Confirming Directories:
Manifest Directory: /home/user/.ollama/models/manifests/registry.ollama.ai
Blob Directory: /home/user/.ollama/models/blobs
Output Models Directory: /path/to/script/Output
Output Models Directory Confirmed.

Available Ollama Models to Convert:

1. model1 (Manifest: manifest1.json, Quantization: q4_0, Size: 1.23 MB)
2. model2 (Manifest: manifest2.json, Quantization: q4_1, Size: 2.34 MB)

Enter the number of the model you want to convert (or 0 to exit): 1
reading layers
[model1] [application/octet-stream]	Blob SHA File Path : [/home/user/.ollama/models/blobs/sha256-abc123] Reading
Successfully converted /home/user/.ollama/models/manifests/registry.ollama.ai/model1/manifest1.json to GGUF.
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request with your changes.## Contact

For any questions or issues, please contact
