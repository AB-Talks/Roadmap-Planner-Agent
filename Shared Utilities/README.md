# Shared Utilities

## Overview
This folder contains common helper functions and the `gemini_core` module, which standardizes how all other agents communicate with the Gemini LLM API. 

## Contents
- **`gemini_core.py`**: Centralized wrapper for Google Generative AI, handling retries, schema enforcement, and model configuration.
- **`__init__.py`**: Module initializer.

## Usage
```python
from shared_utilities.gemini_core import call_gemini

response = call_gemini(prompt="Analyze this...", schema=MyPydanticModel)
```
