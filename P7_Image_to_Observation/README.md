# P7 — Image to Observation for Machine Learning

## 📌 Practical Information

| Field              | Details                                                   |
| ------------------ | --------------------------------------------------------- |
| **Practical No.**  | P7                                                        |
| **Practical Name** | Convert an Image into an Observation for Machine Learning |
| **Course Outcome** | CO1                                                       |
| **Hours**          | 8                                                         |

---

## 🎯 Aim

To convert an image into a numerical **observation/vector** that can be used as input for a machine learning algorithm.

---

## 📚 Objectives

The objectives of this practical are:

* Understand how digital images are represented as numerical data.
* Read an image using Python.
* Convert image data into a numerical array.
* Reshape image pixels into a one-dimensional observation.
* Understand the relationship between image dimensions and feature representation.
* Prepare image data as input for machine learning algorithms.

---

## 🧠 Image Representation in Machine Learning

A digital image is represented as a collection of **pixel values**.

For a grayscale image, each pixel generally contains an intensity value. For a color image, each pixel contains multiple channel values such as **Red, Green, and Blue (RGB)**.

For example:

```text
Image
  ↓
Pixel Values
  ↓
Numerical Array
  ↓
Flatten / Reshape
  ↓
One-Dimensional Observation
  ↓
Machine Learning Input
```

---

## 🛠️ Technologies Used

* **Python**
* **Jupyter Notebook**
* **NumPy**
* **PIL (Pillow)**

---

## 📂 Project Structure

```text
P7_Image_to_Observation/
│
├── P7_Image_to_Observation.ipynb
├── image.jpg
└── README.md
```

---

## 📦 Libraries Used

```python
import numpy as np
from PIL import Image
```

---

## 🖼️ Loading the Image

The image can be loaded using the Pillow library.

```python
image = Image.open("image.jpg")
```

The image dimensions can be checked using:

```python
print(image.size)
```

---

## 🔢 Converting Image to Array

The image is converted into a NumPy array.

```python
image_array = np.array(image)

print(image_array)
```

The NumPy array contains the numerical pixel values of the image.

---

## 📏 Checking Image Shape

The shape of the image array can be checked using:

```python
print(image_array.shape)
```

For example, a grayscale image with dimensions **5 × 5** has:

```text
(5, 5)
```

A color RGB image with dimensions **5 × 5** has:

```text
(5, 5, 3)
```

where `3` represents the RGB color channels.

---

## 🔄 Converting Image into an Observation

To use an image as a single observation in a machine learning model, the image can be flattened into a one-dimensional array.

```python
observation = image_array.reshape(1, -1)

print(observation)
```

The `reshape(1, -1)` operation converts the image into:

```text
1 observation × number of pixel features
```

For example:

```text
Original Image Shape
(5, 5)
      ↓
Flatten
      ↓
Observation Shape
(1, 25)
```

---

## 📊 Observation Shape

The shape of the resulting observation can be checked using:

```python
print(observation.shape)
```

For the example above, the output is:

```text
(1, 25)
```

This means:

* `1` → one image/observation
* `25` → 25 pixel-based features

---

## 🧠 Why Convert an Image into an Observation?

Machine learning algorithms generally require numerical input.

An image contains pixels arranged in a two-dimensional or three-dimensional structure. Converting the image into a numerical observation allows it to be represented as a feature vector.

```text
Image
5 × 5 Pixels
     ↓
25 Pixel Values
     ↓
1 × 25 Observation
     ↓
Machine Learning Model
```

---

## 🔄 Workflow

```text
Start
  ↓
Load Image
  ↓
Check Image Dimensions
  ↓
Convert Image to NumPy Array
  ↓
Check Array Shape
  ↓
Flatten / Reshape Image
  ↓
Create One-Dimensional Observation
  ↓
Check Observation Shape
  ↓
Use as Machine Learning Input
  ↓
End
```

---

## 📈 Before and After Conversion

### Before Conversion

The image is represented as a multi-dimensional array:

```text
Image
   ↓
Rows × Columns × Channels
```

### After Conversion

The image is represented as a single observation:

```text
1 × Number of Pixel Features
```

For example:

```text
Image Shape:       (5, 5)
Observation Shape: (1, 25)
```

---

## 🎓 Learning Outcomes

After completing this practical, the following concepts are understood:

* Understanding digital image representation.
* Understanding pixel values.
* Reading images using Python.
* Converting images into NumPy arrays.
* Understanding image dimensions and array shapes.
* Flattening image data into a feature vector.
* Converting an image into a machine learning observation.
* Preparing image data for machine learning algorithms.

---

## ✅ Result

The image was successfully converted into a **numerical observation** using Python, Pillow, and NumPy.

The image data was represented as numerical pixel values and reshaped into a one-dimensional observation suitable for use as input to a machine learning model.

For the practical example:

```text
Input Shape:  (5, 5)
Output Shape: (1, 25)
```

---

## ⚙️ Requirements

Install the required libraries using:

```bash
pip install numpy pillow
```

---

## ▶️ How to Run

### Step 1: Open Jupyter Notebook

Run:

```bash
jupyter notebook
```

### Step 2: Open the Practical

Navigate to:

```text
P7_Image_to_Observation/
```

and open:

```text
P7_Image_to_Observation.ipynb
```

### Step 3: Add the Image

Place the required image inside the practical folder:

```text
image.jpg
```

### Step 4: Execute the Notebook

Run all cells sequentially to:

1. Load the image.
2. Check the image dimensions.
3. Convert the image into a NumPy array.
4. Display the array shape.
5. Reshape the image data.
6. Create the machine learning observation.
7. Display the observation shape.

---

## 👩‍💻 Author

**Armi Sherathiya**

*AI/ML Engineer | Data Scientist*
