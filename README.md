# Background Remover
A simple web application for removing image backgrounds. The frontend submits an image to a FastAPI backend, which returns a PNG with the background removed.

Additional backend logic added (CORS, fastapi Response) to allow full functionality.

This project is based on the freeCodeCamp tutorial, [How to Go From Hello World to Building Real-World Applications](https://www.freecodecamp.org/news/how-to-go-from-hello-world-to-building-real-world-applications/).

## Backend

Install the Python dependencies from the `backend` directory:

```bash
pip install -r requirements.txt
```

Start the API server from the `backend` directory:

```bash
uvicorn api.main:app --reload
```

Check the server status:

```bash
curl http://localhost:8000/health
```

Test background removal with a local image:

```bash
curl -X POST -F "file=@test_photo.webp" http://localhost:8000/remove-bg --output result.png
```

## Model

The application uses the `u2net.onnx` model from the [`rembg` project](https://github.com/danielgatis/rembg/releases/download/v0.0.0/u2net.onnx).
