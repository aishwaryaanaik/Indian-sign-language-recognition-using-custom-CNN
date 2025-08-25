# Indian Sign Language Recognition using Custom CNN (MobileNetV2)

## Introduction  
Communication barriers can create exclusion for individuals with speech or hearing impairments, limiting access to education, healthcare, and social opportunities.  
This project presents an **Indian Sign Language (ISL) recognition system** that converts sign gestures into **multilingual text and audio**, enabling more inclusive communication.  


## Objectives  
- Recognize Indian Sign Language (ISL) gestures from video input.  
- Translate recognized text into **multiple Indian languages** using translation APIs.  
- Convert translated text into **speech/audio output** for accessibility.  


##  Dataset  
<p align="center">
<img width="300" height="400" alt="image" src="https://github.com/user-attachments/assets/f92a521d-04cc-419b-a817-124c237f214c" />
</p>

- **Custom Dataset**: 20 commonly used English words.  
- **Collection**: 5 samples per word from 5 individuals → introduces variability.  
- **Video Specs**: 10 sec duration, 1080p resolution, 30 FPS.  
- **Background**: Plain black/white for consistency.  
- **Frames**: ~30,000 extracted frames used for training.  
- Dataset Link: [Google Drive](https://drive.google.com/drive/folders/11yHO6M1HWXpZ693wADESBAR1TpOWvcj)  


## Methodology  
<p align="center">
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/6bdf21d1-ff25-4c6a-a6a4-eaf919d080ed" />
</p>

1. **Dataset Creation**  
   - Captured ISL gestures for 20 words.  
   - Extracted frames for gesture transitions.  

2. **Preprocessing**  
   - Frames resized to `224×224` to match MobileNetV2 input.  

3. **Feature Extraction**  
   - Used **pretrained MobileNetV2** (trained on ImageNet).  
   - Extracted visual patterns: edges, shapes, textures.  

4. **Model Architecture**  
   - Global Average Pooling → Dense Layer (512 units).  
   - Dropout (50%) → prevents overfitting.  
   - Softmax Layer → outputs class probabilities.  

5. **Output Pipeline**  
   - Predicted text → passed to Translation API.  
   - Translated text → converted into speech.  
   - Supports **12 Indian languages** (Hindi, Kannada, Tamil, Bengali, etc.).  



## Results  
- **Training Accuracy**: 86%  
- **Validation Accuracy**: 90%

   <p align="center">
  <img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/cb99fbec-0829-4b3a-9ab7-3dd104131480" />
</p>

- Successfully recognized words like *“Energy”* and translated into **12 regional languages**.
   <p align="center">
<img width="400" height="600" alt="image" src="https://github.com/user-attachments/assets/d458e446-db04-4aa6-bf62-69e9062a5914" />
</p>


## Future Scope  
- Use **Temporal Models** (LSTMs/Transformers) for continuous gesture recognition.  
- Expand dataset with more words, varied backgrounds, and more signers.  
- Add **multimodal inputs** (facial expressions, body posture, keypoints).  
- Optimize model for **deployment on edge devices** (FPGA, mobile).

## Co-authors
-Annapurna S.B,Tejaswini Sattikar



