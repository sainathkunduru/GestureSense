# GestureSense

**Author:** Sai Nath ([@sainathkunduru](https://github.com/sainathkunduru))

A real-time hand gesture recognition system using Google's MediaPipe for hand landmark detection and a simple MLP classifier for gesture classification. Recognizes both static hand signs and dynamic finger gestures through a webcam feed.

## Features

- **Real-time hand sign recognition** using webcam
- **Finger gesture tracking** with coordinate history
- **MediaPipe integration** for robust hand landmark detection
- **TFLite models** for fast on-device inference
- **Training notebooks** included for custom gesture training
- **Configurable** detection and tracking confidence thresholds

## Requirements

- Python 3.8+
- MediaPipe 0.8.1+
- OpenCV 3.4.2+
- TensorFlow 2.3.0+
- scikit-learn 0.23.2+ (for confusion matrix)
- matplotlib 3.3.2+ (for visualization)

## Quick Start

```bash
git clone https://github.com/sainathkunduru/GestureSense.git
cd GestureSense
```

Run the demo with your webcam:
```bash
python app.py
```

### Command-line Options

| Option | Description | Default |
|--------|-------------|---------|
| `--device` | Camera device number | 0 |
| `--width` | Camera capture width | 960 |
| `--height` | Camera capture height | 540 |
| `--use_static_image_mode` | Use static image mode | Off |
| `--min_detection_confidence` | Detection confidence threshold | 0.5 |
| `--min_tracking_confidence` | Tracking confidence threshold | 0.5 |

## Project Structure

```
├── app.py                              # Main inference program
├── keypoint_classification.ipynb       # Hand sign training notebook
├── point_history_classification.ipynb  # Finger gesture training notebook
├── model/
│   ├── keypoint_classifier/            # Hand sign recognition model
│   │   ├── keypoint.csv                # Training data
│   │   ├── keypoint_classifier.tflite  # Trained model
│   │   ├── keypoint_classifier.py      # Inference module
│   │   └── keypoint_classifier_label.csv
│   └── point_history_classifier/       # Finger gesture recognition model
│       ├── point_history.csv           # Training data
│       ├── point_history_classifier.tflite
│       ├── point_history_classifier.py
│       └── point_history_classifier_label.csv
└── utils/
    └── cvfpscalc.py                    # FPS calculation utility
```

## Training Custom Gestures

1. Run `app.py` and press `k` to enter keypoint collection mode
2. Perform your gesture and press a number key (0-9) to label it
3. Open `keypoint_classification.ipynb` to train the model
4. The new `.tflite` model is saved automatically

## License

Apache License 2.0

## Contact

**Sai Nath** — [sainathreddykunduru@gmail.com](mailto:sainathreddykunduru@gmail.com)
