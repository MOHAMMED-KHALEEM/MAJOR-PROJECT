# Flask Language Detection Application

A Flask-based web application for detecting languages in text using the `langdetect` library.

## Features

- Language detection from text input
- Dashboard with statistics
- Visualization of detection results
- Comparison between existing and proposed detection methods

## Requirements

- Python 3.7 or higher
- pip (Python package manager)

## Installation & Setup

### Option 1: Using the Batch Script (Windows)

1. Double-click `run.bat` - it will automatically:
   - Create a virtual environment (if it doesn't exist)
   - Install all required dependencies
   - Start the Flask application

### Option 2: Manual Setup

1. **Create a virtual environment:**
   ```bash
   python -m venv venv
   ```

2. **Activate the virtual environment:**
   - Windows:
     ```bash
     venv\Scripts\activate
     ```
   - Linux/Mac:
     ```bash
     source venv/bin/activate
     ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the application:**
   ```bash
   python app.py
   ```

## Running the Application

After installation, the application will be available at:
- **URL:** http://localhost:5000
- **Port:** 5000 (default)

Open your web browser and navigate to `http://localhost:5000` to use the application.

## Project Structure

```
FlaskLinguaDetect/
├── app.py                 # Main Flask application
├── forms.py               # WTForms form definitions
├── requirements.txt       # Python dependencies
├── run.bat               # Windows run script
├── static/
│   └── style.css         # CSS styles
└── templates/
    ├── base.html         # Base template
    ├── home.html         # Home page
    ├── dashboard.html    # Dashboard page
    ├── visualization.html # Visualization page
    ├── predict_existing.html
    ├── predict_proposed.html
    └── partials/
        └── footer.html
```

## Dependencies

- **Flask** - Web framework
- **Flask-WTF** - Form handling
- **WTForms** - Form validation
- **langdetect** - Language detection library

## Usage

1. Navigate to the application in your browser
2. Go to the "Predict" section
3. Enter text in the text area
4. Click "Detect Language" to see the results
5. View statistics in the Dashboard
6. See visualizations in the Visualization section

## Stopping the Application

Press `Ctrl+C` in the terminal/command prompt to stop the Flask server.
