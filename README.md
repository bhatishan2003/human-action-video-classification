# Human Action Video Classification

## Introduction

This project implements a human action recognition system using deep learning. It classifies videos into one of six action categories: walking, jogging, running, boxing, handwaving, and handclapping. The model uses a Convolutional Neural Network (CNN) for feature extraction from video frames combined with a Recurrent Neural Network (RNN) for temporal sequence modeling.

The project is trained and evaluated on the KTH Human Action Dataset, a benchmark dataset for human action recognition in videos.

```bash
pip install -r requirements.txt
```

## Dataset

The project uses the KTH Human Action Dataset. The dataset should be placed in the `data/kth_actions/` directory with the following structure:

```
data/kth_actions/
├── boxing/
├── handclapping/
├── handwaving/
├── jogging/
├── running/
└── walking/
```

Each subdirectory contains video files for the respective action.

## Training

To train the model, run:

```bash
python train.py
```

This will train the model for 5 epochs by default. You can modify the configuration in the script or pass command-line arguments.

The trained model checkpoints will be saved in the `checkpoints/` directory.

## Prediction

To classify a single video, use:

```bash
python predict_video.py --video path/to/your/video.avi
```

The script will output the predicted action class.

## Model Architecture

- **CNN Encoder**: 3 convolutional blocks with batch normalization and max pooling
- **RNN**: Simple RNN for sequence modeling
- **Output**: 6-class classification

## Results

### Training Curves

![Training Curves](assets/training_curves.png)

## Contributing

Feel free to open issues or submit pull requests for improvements.

## License

This project is open-source. Please check for any applicable licenses.

## Development Notes

- Pre-commit

    We use pre-commit to automate linting of our codebase.
    - Install hooks:
        ```bash
        pre-commit install
        ```
    - Run Hooks manually (optional):
        ```bash
        pre-commit run --all-files
        ```

- Ruff:
    - Lint and format:
        ```bash
        ruff check --fix
        ruff format
        ```
