# HidroGreen Detection Service

This service detects plant diseases using a machine learning model. It provides an API endpoint that accepts plant images and returns the predicted disease class along with a confidence score.

## Supported Disease Classes

- Miner
- No disease
- Phoma
- Red spider
- Rust

## Requirements

- Python 3.12 or higher
- Poetry (for dependency management)

## Installation

1. Clone this repository

2. Navigate to the project directory

```powershell
cd path\to\DetectionService
```

3. Install dependencies using Poetry

```powershell
poetry install
```

## Running the Service

1. Start the service using Poetry

```powershell
poetry run fastapi dev
```

The service will start on `http://127.0.0.1:8000` by default.

## API Endpoints

### GET /

Returns a simple health check message.

**Response:**
```json
{
  "Hello": "World"
}
```

### POST /predict

Upload an image file to get disease prediction.

**Request:**
- Method: POST
- Endpoint: `/predict`
- Content-Type: `multipart/form-data`
- Body: Image file (field name: `file`)

**Response:**
```json
{
  "predicted_class": "nodisease",
  "confidence": 0.9876
}
```

## Example Usage

Using PowerShell and curl:

```powershell
curl -F "file=@path\to\plant_image.jpg" http://localhost:8000/predict
```

## Development

This project uses:
- FastAPI for the web server
- TensorFlow for the machine learning model
- Poetry for dependency management

The model file should be placed in the `model` directory as `model-8678.keras`.
