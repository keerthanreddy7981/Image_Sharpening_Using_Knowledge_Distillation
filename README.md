# Image Sharpening using Knowledge Distillation
Overview :
This project focuses on enhancing image sharpness for real-time applications such as video conferencing, mobile photography, and low-bandwidth streaming.
It implements a Teacher–Student Knowledge Distillation framework, where:

Teacher Model: A high-performance SwinIR model (Swin Transformer for Image Restoration)

Student Model: A lightweight CNN-based network designed for real-time execution

The student model learns from the teacher to replicate its image restoration capabilities while requiring significantly fewer computational resources, making it suitable for resource-constrained devices.

 Objective :
Enhance image clarity for degraded or blurred images.

Achieve real-time performance (30–60 FPS) on 1080p resolution.

Maintain high perceptual quality with SSIM > 90%.

Enable deployment in low-bandwidth environments like video conferencing.

 Approach :
Data Preparation

High-resolution images from DIV2K dataset were downscaled using bicubic interpolation to simulate blur.

Images were then paired (blurred → sharp) for supervised learning.

Teacher–Student Framework

Teacher: SwinIR model generates high-quality sharpened outputs.

Student: Lightweight CNN with residual connections learns from both ground truth and teacher outputs.

Loss Functions

MSE Loss between predictions and ground truth.

Knowledge Distillation Loss to mimic the teacher model’s output.

Evaluation Metrics

SSIM (Structural Similarity Index)

PSNR (Peak Signal-to-Noise Ratio)

MOS (Mean Opinion Score from user studies)

 Tools and Technologies :
Programming Language: Python

Framework: PyTorch

Teacher Model: SwinIR

Student Model: Custom lightweight CNN

Libraries: TorchVision, NumPy, Pillow, Matplotlib, tqdm

Dataset: DIV2K

 Key Achievements:
90%+ SSIM on multiple categories (text, nature, people, animals, games).

Real-time inference on 1080p images.

Significant reduction in model size and computational cost.

 References :
SwinIR: Image Restoration Using Swin Transformer
