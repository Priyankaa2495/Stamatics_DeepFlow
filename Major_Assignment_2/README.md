# Dog Breed Identification with Transfer Learning

##  Model Architecture
- Base Model: **MobileNetV2** (pretrained on ImageNet)
- Custom Head:
  - GlobalAveragePooling2D
  - Dense(256, ReLU)
  - Dropout(0.6)
  - Dense({len(breed_to_index)}, softmax)

##  Transfer Learning Strategy
- Base model was **frozen**
- Custom head was trained for 10 epochs
- No data augmentation used
- L2 Regularization: 1e-4  
- Dropout: 0.6

##  Performance
- Final Validation Accuracy: **{val_acc:.4f}** 
- Final Validation Loss: **{val_loss:.4f}** 

##  Files Included
- `cnn_model.h5` - Trained model
- `submission.csv` - Predictions on test set
- `notebook.ipynb` - Training + inference**
