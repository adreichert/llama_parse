# Llama Parser (Preview)

Llama Parser is an API created by LlamaIndex to effeciently parse and represent files for effecient retrieval and context augmentation using LlamaIndex frameworks.

Available for free as a preivew, you can try it out today.

**NOTE:** Currently, only PDF files are supported.

## Getting Started

First, login and get an api-key from `https://cloud.llamaindex.ai`.

Simply install the package:

`pip install llama-parser`

Then, you can run the following to parse your first PDF file:

```python
from llama_parser import LlamaParser

parser = LlamaParser(
    api_key="...",  # can also be set in your env as LLAMA_CLOUD_API_KEY
    result_type="markdown"  # "markdown" and "text" are available
)

# sync
documents = parser.load_data("./my_file.pdf")

# async
documents = await parser.aload_data("./my_file.pdf")
```

## Using with `SimpleDirectoryReader`

You can also integrate the parser as the default PDF loader in `SimpleDirectoryReader`:

```python
from llama_parser import LlamaParser
from llama_index import SimpleDirectoryReader

parser = LlamaParser(
    api_key="...",  # can also be set in your env as LLAMA_CLOUD_API_KEY
    result_type="markdown"  # "markdown" and "text" are available
)

file_extractor = {".pdf": parser}
documents = SimpleDirectoryReader("./data", file_extractor=file_extractor).load_data()
```

Full documentation for `SimpleDirectoryReader` can be found on the [LlamaIndex Documentation](https://docs.llamaindex.ai/en/stable/module_guides/loading/simpledirectoryreader.html).

## Raw API usage

<todo?>

## Examples

Serveral end-to-end indexing examples can be found in the examples folder

- ?
- ?
- ?