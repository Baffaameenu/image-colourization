# image-colourization
autoencoder
# Image Colorization with Autoencoder (PyTorch)

Quick starter for image colorization using a U-Net style autoencoder.

Requirements
- Python 3.8+
- torch, torchvision
- scikit-image
- pillow
- numpy

Usage
1. Put training images in an ImageFolder layout (or use torchvision datasets like CIFAR/STL).
2. Edit `train.py` or supply CLI args:
   - `--data /path/to/images`
   - `--epochs 50`
   - `--batch-size 16`
3. Run:
   ```
   python train.py --data /path/to/images --epochs 30 --batch-size 16 --size 256
   ```

Files
- dataset.py: dataset that yields L (1,H,W) and ab (2,H,W) tensors
- model.py: U-Net like autoencoder mapping L -> ab
- train.py: training loop, saving models & sample images
- utils.py: helper visualize & conversions

Notes & next steps
- Switch to perceptual / adversarial / classification loss for better colors.
- Try pretrained encoder (ImageNet) as encoder backbone to improve features.
- Experiment with rebalancing ab-channels (see Zhang et al., 2016).
- 
