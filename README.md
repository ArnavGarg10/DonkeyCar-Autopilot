# DonkeyCar Autopilot

This guide will walk you through downloading our pre-trained DonkeyCar model, importing it into your project, and running your car using the model for autonomous driving.

---

## Prerequisites

Ensure you have the following before proceeding:

- DonkeyCar is installed on your Raspberry Pi or local machine
- A DonkeyCar project is already created using:
  ```bash
  donkey createcar --path ~/my_car
  ```
- Internet connection to download the model
- DonkeyCar vehicle setup and connected

---

## Step 1: Download the Pre-trained Model

You can download the pre-trained model (`rnn4.tflite`) from our github by clicking on the file and download it.

Upload your `rnn4.tflite` model to the `models/` folder under your `my_car` directory.

---

## Step 2: Ensure the model is placed correctly

Make sure the model file is located at:

```
~/my_car/models/rnn4.tflite
```

---

## Step 3: Run the Car in Autonomous Mode

Launch your DonkeyCar vehicle with the model:

```bash
cd ~/my_car
python manage.py drive --model models/rnn4.tflite --type tflite_rnn
```

---

## Want to Custom Train the Model?

If you'd rather collect data and train your own model, download our training data by signing up for the intermediate plan and then run:

```bash
python manage.py drive  # use manual mode
```

Then train a model:

```bash
python train.py --tub ./data --model ./models/mypilot.h5 --type rnn
```

---

## Troubleshooting

- **Model not found?**  
  Ensure the file path is correct and that the `.tflite` file exists in the specified directory.
  
- **Package donkey not found?**  
  Make sure that your conda virtual environment with Donkeycar installed on it is active.
---

## Resources

- [DonkeyCar Documentation](https://docs.donkeycar.com/)
- [Installation Video](https://youtu.be/J6Ll5Obtuxk?si=xSyy9eqBwJZcUoA0)

---

Happy racing! 🏁
