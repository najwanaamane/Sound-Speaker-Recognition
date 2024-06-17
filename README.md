

# Automatic Speaker Recognition: Identification and Verification

## Overview

This project focuses on the automatic recognition of speakers using advanced techniques such as Mel-frequency cepstral coefficients (MFCC) and Gaussian Mixture Models (GMM). The objective is to build a system that can identify and verify speakers based on their unique vocal characteristics.

## Project Structure   
![image](https://github.com/najwanaamane/Sound-Speaker-Recognition/assets/86806375/dde643bb-f349-4338-b84c-2eb77da7fac6)


### 1. Dataset

- **Audio Collection**: Audio recordings of speakers in classical Arabic.
- **Data Storage**: Audio files are organized into 'Train' and 'Test' folders, each containing subfolders for male (H) and female (F) speakers. Each subfolder contains multiple one-minute recordings.

### 2. Audio Processing

- **Reading Audio**: Use the `read_audios` function to read audio files from specified directories using the `Scipy` library.
- **MFCC Extraction and Silence Removal**: Use the `extractMfccs_RemoveSilence_saveMfccs` function to extract MFCC features and remove silent frames, then save these features into text files.

### 3. Data Segmentation

- **Segmenting Data**: Split the MFCC files into segments of 3s, 10s, 15s, and 30s for testing the model's performance across different durations.

### 4. Model Training

- **GMM Initialization**: Use the `gmm` function to initialize and train GMM models with various numbers of components (16, 32, 128, 256) for each speaker.
- **Model Storage**: Save the trained GMM models into `.pkl` files for future use.

### 5. Speaker Identification

- **Prediction Function**: Use the `predict_speaker` function to predict the speaker by calculating the log-likelihood scores of the MFCC features under each GMM model.

### 6. Speaker Verification

- **Verification Scores**: Use the `get_scores` function to compute scores for test segments with each GMM model.
- **DET Curves**: Generate Detection Error Tradeoff (DET) curves to evaluate the performance of the speaker verification system.

## Detailed Process

### Data Collection

Audio recordings are collected and organized into a structured dataset. Each recording is preprocessed to create longer, coherent audio segments for each speaker, facilitating effective model training and evaluation.

### Audio Processing

- **Reading Audio**: The `read_audios` function reads and processes the audio files.
- **MFCC Extraction**: Extracts the MFCC features, which capture the essential characteristics of the audio signals.
- **Silence Removal**: Removes silent frames to improve the quality of the feature set.

### Data Segmentation

Segments the MFCC features into various lengths (3s, 10s, 15s, 30s) to analyze the impact of segment duration on model performance.

### Model Training

Trains multiple GMM models with different numbers of components, storing each trained model for further use in identification and verification tasks.

### Speaker Identification

Predicts the speaker by comparing the log-likelihood scores of the MFCC features against the trained GMM models. The highest score indicates the most likely speaker.

### Speaker Verification

Evaluates the system's performance using DET curves, plotting the trade-off between false acceptance rates (FAR) and false rejection rates (FRR) to assess the accuracy and reliability of the verification process.

## Results and Interpretations

### Identification   

![image](https://github.com/najwanaamane/Sound-Speaker-Recognition/assets/86806375/30c29d86-a61d-4e97-ab9a-002ff030184f)


- **Best Models**: GMM models with 16 and 32 components performed best.
- **Optimal Segment Length**: 10-second segments yielded the best results.
- **Gender Differences**: Higher false prediction rates for female speakers compared to male speakers.

### Verification   
overview of some gmm det curves      
![image](https://github.com/najwanaamane/Sound-Speaker-Recognition/assets/86806375/2b5b4ff2-717c-4375-8634-39ad053f7791)   
![image](https://github.com/najwanaamane/Sound-Speaker-Recognition/assets/86806375/40ffd886-38a9-4ee4-aea0-b71c4f8fef12)   
![image](https://github.com/najwanaamane/Sound-Speaker-Recognition/assets/86806375/1281e629-3d0d-4725-b963-9fab8b1759a7)





- **DET Curves**: Most curves are close to the lower left corner of the graph, indicating good model performance.
- **EER**: Equal Error Rates (EER) are close to zero, suggesting high accuracy and discrimination capabilities.

  

## Conclusion

The project successfully developed a system for automatic speaker identification and verification, demonstrating significant potential for applications in security, telephony, and intelligent voice assistants. Future improvements could focus on enhancing dataset quality and exploring advanced techniques for even better performance.

## Authors and Acknowledgments

- **Author**: Najwa Naamane
- **Supervisor**: Prof. Jamal ElKharroubi


---

### Usage Instructions


 **Run Jupyter Notebooks**:
    - **Audio Processing**: Open and run `Splitting-Test-And-Saving.ipynb`
    - **Model Training**: Open and run `training.ipynb`
    - **Speaker Identification**: Open and run `identification.ipynb`
    - **Speaker Verification**: Open and run `Verification-Female.ipynb`, `Verification-Female.ipynb`

