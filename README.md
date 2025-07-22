# 🎨 Generating Images from Sketches using GANs

This project focuses on translating hand-drawn sketches into photorealistic images using Conditional GANs (CGANs), with facial attributes as guidance. The system implements deep generative models to produce realistic facial outputs, with the CelebA dataset as the primary source for training.

---

## 🧠 Project Overview

We implemented and evaluated multiple GAN architectures for sketch-to-image synthesis. The models are trained to map sketches to photo-realistic outputs, incorporating facial attribute conditioning to improve realism and control.

The key idea is to enhance generation accuracy using attributes like **gender, smile, age**, etc., combined with structural sketch input.

---

## 📌 Key Features

- ✅ Converts grayscale face sketches to photorealistic colored images  
- ✅ Attribute-guided image generation using Conditional GANs  
- ✅ Implements CNN, LSTM, UNet-like encoder-decoder architecture  
- ✅ Includes self-attention & multi-scale layers for finer image quality  
- ✅ Trained and evaluated on CelebA dataset

---

## 🧪 Research Foundation

The project draws inspiration and methodology from multiple peer-reviewed papers:

1. **Facial Attributes Guided Deep Sketch-to-Photo Synthesis**  
2. **Sketch-to-Color Image with GANs**  
3. **Generating Photographic Faces from the Sketch Guided by Attribute Using GAN**  
4. **Multi-Scale Gradients Self-Attention Residual Learning for Sketch-Photo Transformation**  
5. **Unsupervised Sketch-to-Image Translation Network**  

These were analyzed and compared in terms of architecture, performance (FID, attribute realism), and computational cost.

---

## 🏗️ System Architecture

```
Input Sketch + Attributes
        ↓
[ Preprocessing ]
        ↓
[ Generator Network ]
        ↓
[ Discriminator Network ]
        ↓
Generated Photo Output
```

- The generator fuses sketch and attribute features and passes them through downsampling, attention, and upsampling blocks.
- The discriminator evaluates the realism of the output image and its consistency with input attributes.

---

## 📂 Dataset

- **CelebA Dataset** (Aligned & Cropped 128x128)
- Each image is associated with 40 facial attribute labels
- Sketches were generated using Canny edge detection or extracted from existing datasets

---

## 🧰 Technologies Used

| Component       | Tech Used              |
|----------------|------------------------|
| ML Framework   | TensorFlow, PyTorch    |
| Core Models    | Conditional GAN, UNet  |
| Image Processing | OpenCV, PIL           |
| Loss Functions | Binary Crossentropy, L1 Loss (optional) |
| Evaluation     | Fréchet Inception Distance (FID), Attribute Accuracy |

---

## 🚀 Setup Instructions

```bash
git clone https://github.com/satyambittu/Generating-Images-from-Sketches
cd Generating-Images-from-Sketches
pip install -r requirements.txt
```

---

## 🧪 Training

```bash
python train.py
```

Training parameters can be configured inside `train.py` (epochs, batch size, learning rate, etc.).

---

## 🔍 Inference

```bash
python generate.py --sketch path/to/sketch.png --attributes path/to/attr.json
```

Outputs will be saved in `/results`.

---

## 🎯 Results

| Sketch | Generated Image |
|--------|------------------|
| ![](samples/input1.png) | ![](samples/output1.png) |
| ![](samples/input2.png) | ![](samples/output2.png) |

---

## 📈 Performance

- CNN + LSTM hybrid showed the best FID score across test batches  
- Attribute-conditional generation reduced error in identity matching  
- Model generalizes well across gender, age, and smile attributes

---

## 🧭 Future Work

- Improve model speed with lightweight GAN variants  
- Add interactive web interface for real-time sketch-to-image  
- Explore cross-domain applications: anime, apparel design, product prototyping

---

## 📚 References

- [CelebA Dataset](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html)
- [Pix2Pix Paper](https://arxiv.org/abs/1611.07004)
- [Conditional GAN](https://arxiv.org/abs/1411.1784)
- Full SRS documentation available in `/docs/srs_report.pdf`

---

## 🧑‍💻 Author

[Satyam Kumar](https://github.com/satyambittu)  
Project Repository: [https://github.com/satyambittu/Generating-Images-from-Sketches](https://github.com/satyambittu/Generating-Images-from-Sketches)
