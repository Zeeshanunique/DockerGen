# Text Generation API with FastAPI

This repository contains a simple text generation API built using FastAPI and the Hugging Face Transformers library. The API uses a pre-trained model to generate text based on input provided by the user.

## Features

- A home route (`/`) that returns a welcome message.
- A text generation route (`/generate`) that takes a string input and returns generated text using the `google/flan-t5-small` model.

## Requirements

- Python 3.7+
- FastAPI
- Transformers from Hugging Face

## Installation

1. **Clone the repository:**

    ```bash
    git clone <repository-url>
    cd <repository-directory>
    ```

2. **Create a virtual environment:**

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. **Install the dependencies:**

    ```bash
    pip install fastapi[all] transformers
    ```

## Running the Application

1. **Start the FastAPI server:**

    ```bash
    uvicorn main:app --reload
    ```

2. **Navigate to the API documentation:**

    Open your browser and go to `http://127.0.0.1:8000/docs` to see the interactive API documentation provided by Swagger UI.

## API Endpoints

### Home

- **URL:** `/`
- **Method:** GET
- **Description:** Returns a welcome message.
- **Response:**
  ```json
  {
    "message": "Hello World"
  }
  ```

### Generate Text

- **URL:** `/generate`
- **Method:** GET
- **Query Parameter:**
  - `text` (string): The input text based on which the model will generate text.
- **Description:** Generates text based on the input string using the `google/flan-t5-small` model.
- **Response:**
  ```json
  {
    "output": "Generated text based on the input"
  }
  ```

## Example Usage

### Home Endpoint

To access the home endpoint, send a GET request to:

```bash
curl -X 'GET' \
  'http://127.0.0.1:8000/' \
  -H 'accept: application/json'
```

### Generate Text Endpoint

To generate text, send a GET request to:

```bash
curl -X 'GET' \
  'http://127.0.0.1:8000/generate?text=your_input_text' \
  -H 'accept: application/json'
```

Replace `your_input_text` with the text you want to provide to the model.

## Notes

- Ensure that you have a stable internet connection as the Hugging Face model might need to download pre-trained weights.
- For production, consider using a more robust server setup and potentially a GPU for faster inference.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Feel free to contribute to this project by opening issues or submitting pull requests.

Happy coding!
