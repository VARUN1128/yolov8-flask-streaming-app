
````markdown
# 🎥 YOLOv8 Flask Streaming App

This repository provides a **web-based real-time object detection application** using the [YOLOv8](https://github.com/ultralytics/ultralytics) model and the [Flask](https://flask.palletsprojects.com/) web framework. It supports detection on both **webcam feeds** and **video files**, and streams results through a live browser interface.

---

## 🚀 Features

- Real-time object detection with YOLOv8
- Stream detection output in-browser (live video)
- Works with both video files and webcam
- Clean Flask-based structure
- Modular code (detection logic separated in `YOLO_Video.py`)

---

## 🧰 Requirements

- Python 3.7+
- Flask
- OpenCV
- Ultralytics YOLOv8

### 📦 Install dependencies

```bash
pip install flask opencv-python ultralytics
````

---

## 📁 Project Structure

```
.
├── app.py                  # Flask web server
├── YOLO_Video.py           # Object detection logic
├── Videos/
│   └── bikes.mp4           # Sample video file
├── YOLO-Weights/
│   └── yolov8n.pt          # YOLOv8 model weights
├── templates/
│   └── index.html          # (Optional) HTML UI if extended
├── static/
│   └── ...                 # (Optional) For CSS or JS
└── README.md
```

---

## ⚙️ How to Run

1. **Clone the repository**:

```bash
git clone https://github.com/your-username/yolov8-flask-streaming-app.git
cd yolov8-flask-streaming-app
```

2. **Add your model weights** to the `YOLO-Weights/` folder (e.g., `yolov8n.pt`).

3. **Add input videos** to the `Videos/` folder if using a file-based input.

4. **Start the Flask app**:

```bash
python app.py
```

By default, the app will run at:

```
http://127.0.0.1:5000/
```

---

## 🌐 Endpoints

* `http://127.0.0.1:5000/video`
  → Runs detection on a pre-specified video file (e.g., `bikes.mp4`)

* `http://127.0.0.1:5000/webcam`
  → Runs detection on the system's webcam (`cv2.VideoCapture(0)`)

> You can add your own routes and customize `generate_frames()` to accept other sources too.

---

## 🧠 How It Works

* `YOLO_Video.py` contains a function `video_detection()` that handles YOLO inference frame-by-frame.
* `generate_frames()` in `app.py` reads each frame, applies detection, encodes it as JPEG, and yields it for browser streaming.
* Flask serves the processed frames to the frontend using `multipart/x-mixed-replace`.

---

## 📌 Notes

* Ensure that your webcam isn’t used by another application before accessing `/webcam`.
* If needed, modify `video_detection()` in `YOLO_Video.py` to change detection behavior or overlay.

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙌 Acknowledgements

* [Ultralytics](https://github.com/ultralytics/ultralytics) for YOLOv8
* [Flask](https://flask.palletsprojects.com/) for web serving
* [OpenCV](https://opencv.org/) for video I/O

---

## 📬 Contact

Feel free to raise an [Issue](https://github.com/your-username/yolov8-flask-streaming-app/issues) or reach out via email for questions or contributions.

```

---

Let me know if you want:
- A sample `YOLO_Video.py` template
- HTML frontend (`index.html`) to add a landing page
- Docker support for deployment
- Gunicorn + Nginx setup for production deployment

I'm happy to help with the next step.
```
