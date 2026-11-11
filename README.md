# NYC Airbnb Room Type Predictor

This project is a small website that predicts the type of an Airbnb listing in New York City. Enter details such as its location, price, reviews, and availability to get a prediction for **entire home**, **private room**, or **shared room**.

> This project predicts room type. It does not predict the nightly price.

<img width="1440" height="673" alt="image" src="https://github.com/user-attachments/assets/5688b8c8-4a72-4dbe-91be-7b8c3d30abf4" />


## What you need

- Python 3.12
- A web browser
- The project files, including `Model_Pipeline.pkl`

## Run the project

The project has two parts: a Python API that makes predictions and a website that you use in your browser. Keep both running while you use the app.

### 1. Open a terminal in the project folder

In VS Code, open this project folder, then choose **Terminal → New Terminal**. The terminal should open in the folder containing `main.py` and `Model_Pipeline.pkl`. If it does not, change to that folder with `cd`, for example:

```bash
cd /path/to/NYC-Airbnb-Room-Type-Predictor
```

Replace `/path/to/` with the location where you saved the project.

### 2. Create an environment and install dependencies

Run these commands in the terminal:

```bash
python3.12 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

On Windows PowerShell, activate the environment with:

```powershell
.\.venv\Scripts\Activate.ps1
```

### 3. Start the prediction API

In the same terminal, run:

```bash
uvicorn main:app --reload
```

Leave this terminal open. The API is running at <http://127.0.0.1:8000>. You can check it by opening <http://127.0.0.1:8000/docs>.

### 4. Start the website

Open a **second terminal** in the same project folder. In VS Code, choose **Terminal → New Terminal** again. Then run:

```bash
python3 -m http.server 5500
```

On Windows, if `python3` is not recognized, use:

```powershell
python -m http.server 5500
```

Leave this terminal open too. Open <http://127.0.0.1:5500> in your browser, fill in the listing details, and select **Predict room type**. Use **Try an example** to fill in sample details.

To stop either server, press **Ctrl+C** in its terminal.

## If something goes wrong

- **The page says the API is unavailable:** Make sure the API command in step 3 is still running.
- **The prediction request fails:** Start both servers and keep them running. The website sends predictions to `http://127.0.0.1:8000`.
- **`python3.12` is not found:** Install Python 3.12, then repeat step 2.
- **`uvicorn` is not found:** Activate the virtual environment and run `python -m pip install -r requirements.txt`.
- **The browser reports `favicon.ico` as 404:** This is harmless; it only means the project does not include a browser-tab icon.

## Project files

- `main.py` — the FastAPI application and prediction API
- `Model_Pipeline.pkl` — the trained model used to make predictions
- `index.html`, `style.css`, `script.js` — the website
- `nyc_airbnb_room_type_classification.ipynb` — the model exploration notebook
- `requirements.txt` — the Python packages needed by the app

  
