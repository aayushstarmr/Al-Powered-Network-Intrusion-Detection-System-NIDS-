# AI-Powered Network Intrusion Detection System (NIDS)

An intelligent, machine-learning-based system to monitor network traffic and detect malicious activities (such as DoS, Probes, R2L, and U2R attacks) in real-time. 

This project simulates network flow, classifies packets using a pre-trained **Random Forest Classifier**, and visualizes the traffic and threat alerts on a modern web dashboard.

## Features
- **Machine Learning Engine**: A `scikit-learn` Random Forest model trained on synthetic network traffic features (inspired by the NSL-KDD dataset).
- **Traffic Simulator**: A background worker that generates live network traffic and feeds it into the AI model for real-time inference.
- **RESTful API**: A Flask backend providing endpoints for live statistics, traffic streams, and threat alerts.
- **Real-Time Dashboard**: A modern HTML/JS interface featuring live-updating charts (via Chart.js) and a threat alert feed.

## Project Structure
- `model/` - Contains the dataset generator, training script (`train.py`), and the inference engine (`detector.py`).
- `static/` & `templates/` - HTML, CSS, and JS files for the dashboard.
- `app.py` - Main Flask API server.
- `monitor.py` - Network traffic simulation and inference worker.
- `Start_NIDS.command` - macOS automation script to run the entire system with one click.

## Installation & Setup

### Prerequisites
- Python 3.8+

### 1. Automated Setup (macOS)
If you are on a Mac, you can simply double-click the `Start_NIDS.command` file. It will automatically create a virtual environment, install dependencies, train the model, start the servers, and open the dashboard in your browser.

### 2. Manual Setup (All OS)

**1. Create a virtual environment and install dependencies:**
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```
*(Note: If you don't have a `requirements.txt`, run `pip install flask scikit-learn pandas numpy sqlalchemy Flask-SQLAlchemy`)*

**2. Train the Model:**
```bash
python model/train.py
```

**3. Start the Flask API Server:**
```bash
python app.py
```

**4. Start the Traffic Simulator:**
Open a **new** terminal, activate your virtual environment, and run:
```bash
python monitor.py
```

**5. View Dashboard:**
Navigate to `http://localhost:5000` in your web browser.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

