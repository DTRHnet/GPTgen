# GPTgen

GPTgen is a command-line utility to generate prompts for OpenAI's GPT models. It supports various modes of prompt generation, allows adding additional variables, and can even get responses from the ChatGPT API directly.

## Features

- Generate prompts with different levels of complexity (normal, intermediate, advanced, custom).
- Include descriptions and examples for each variable.
- Save generated prompts to a file.
- Use predefined jailbreak methods for prompt customization.
- Fetch responses from the OpenAI ChatGPT API.

## Requirements

- Python 3.6+
- `argparse` (standard library)
- `json` (standard library)
- `sys` (standard library)
- `os` (standard library)
- `datetime` (standard library)
- `rich` library
- `openai` library

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/DTRHnet/GPTgen.git
    cd GPTgen
    ```

2. Install required dependencies:
    ```sh
    pip install rich openai
    ```

3. Set your OpenAI API key in the script:
    ```python
    openai.api_key = 'YOUR_OPENAI_API_KEY'
    ```

## Usage

```sh
python GPTgen.py [options]
```

### Options

- `-h, --help`: Show this help message.
- `-d, --description [items]`: Return description of the data for the given list of variables or keywords. If no items are given, return all descriptions.
- `-m, --mode [mode]`: Mode of the prompt generation: normal or 1 (default), intermediate or 2, advanced or 3, custom or 4.
- `-s, --save [file.gptp]`: Save the prompt to a `.gptp` file in JSON format.
- `-j, --jailbreak [method]`: Use a specific jailbreak method (currently available: pliny).
- `-L, --live [model]`: Use the generated prompt to get a response from ChatGPT API and display it in the terminal. If no model is specified, use `gpt-3.5-turbo`.

### Example Commands

1. Generate a normal mode prompt:
    ```sh
    python GPTgen.py --mode normal
    ```

2. Generate an intermediate mode prompt and save it to a file:
    ```sh
    python GPTgen.py --mode intermediate --save myprompt.gptp
    ```

3. Generate an advanced mode prompt and get a response from the ChatGPT API using the `gpt-4` model:
    ```sh
    python GPTgen.py --mode advanced --live gpt-4
    ```

4. Get descriptions of specific variables:
    ```sh
    python GPTgen.py --description "{user_input},{context}"
    ```

## Error Handling

- The script includes error handling for authentication issues with the OpenAI API, insufficient quota errors, and general exceptions.

## Contributing

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a Pull Request.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Contact

For any issues, please open an issue on GitHub or contact the maintainer.

