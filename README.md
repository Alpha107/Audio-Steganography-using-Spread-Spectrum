# Audio Steganography Using Spread Spectrum Techniques

This repository implements an audio steganography project leveraging spread spectrum methodology to embed and extract secret information from audio signals. The technique ensures robustness, imperceptibility, and resilience against signal degradation.

## Introduction

Steganography is the practice of hiding secret information within another medium, such as images, audio, or video. In audio steganography, data is embedded within sound files in such a way that the alterations are undetectable to human hearing.

This project utilizes spread spectrum techniques, a method inspired by telecommunications, to hide data by spreading the information over a wide frequency spectrum. This ensures that the embedded data remains imperceptible while making it robust against noise and compression.

## Spread Spectrum Methodology in Steganography

**1. Principles of Spread Spectrum:**

Spread spectrum techniques spread a narrowband signal over a wide frequency band, which offers the following advantages:

- Low Probability of Detection (LPD): The changes in the carrier signal (audio) are minimal, making the presence of the hidden data difficult to detect.
- Robustness: Spread spectrum is resistant to noise, compression, and other common signal degradations.
- Privacy: Without the correct spreading code, extraction of hidden data is nearly impossible.

**2. Direct Sequence Spread Spectrum (DSSS):**

This project implements DSSS, where:

- A pseudo-random noise (PN) sequence is used to spread the data signal over a wide frequency band.
- The PN sequence is shared between the sender and receiver as a secret key.
- The hidden data is modulated into the carrier signal (audio) by altering the amplitude or phase of the carrier using the PN sequence.

### Key Features of the Project

**1. Imperceptible Embedding:**

- Ensures that the embedded data does not degrade the quality of the audio signal.

- Leverages human auditory limitations to hide information in high-frequency components.

**2. Robustness:**

- Designed to survive common audio operations, such as compression, noise addition, and low-pass filtering.

**3. Security:**

- The use of a pseudo-random sequence ensures that only users with the correct key can retrieve the hidden information.

## Applications

- **Secure Communication:**
Transmitting sensitive information covertly in an audio signal.

- **Digital Watermarking:**
Embedding ownership information in audio files for copyright protection.

- **Covert Channels:**
Establishing secret channels in public audio transmissions.

## Theoretical Background

**1. Signal Representation:**
Audio signals are typically represented as a continuous wave in the time domain. However, spread spectrum operates in both the time and frequency domains, enabling robust embedding by spreading the signal.

**2. Embedding Process:**

- The secret message is modulated using the PN sequence.
- The modulated signal is added to the carrier audio signal in specific frequency bands.
- The resultant audio signal appears unchanged to the human ear but contains the hidden data.

**3. Extraction Process:**

- The receiver applies the same PN sequence to the stego-audio signal.
- By correlating the PN sequence with the stego-audio, the hidden data is retrieved.

**4. Performance Metrics:**

- Signal-to-Noise Ratio (SNR): Measures the imperceptibility of the embedded signal.
- Bit Error Rate (BER): Assesses the accuracy of the extracted data after transmission or processing.
- Payload Capacity: Indicates how much data can be hidden without compromising audio quality.

## Challenges and Solutions

### Challenges:

- Perceptual Limitations:
Human hearing is sensitive to distortions, especially in lower frequencies.

- Channel Distortions:
Compression algorithms like MP3 may remove high-frequency components, potentially destroying hidden data.

- Robustness vs. Imperceptibility:
Balancing these two opposing goals is a key design consideration.

### Solutions:

- Embedding data in higher frequency ranges, where human perception is less sensitive.
- Utilizing error correction codes to recover data in degraded channels.
- Adopting spread spectrum modulation to distribute the hidden data across multiple frequencies.

## Future Work
Potential enhancements to this project include:

- **Adaptive Steganography:**
Dynamically adjusting embedding parameters based on the characteristics of the carrier audio.
- **Hybrid Techniques:**
Combining spread spectrum with other steganographic methods, such as phase encoding, for improved robustness.
- **Encryption:**
Encrypting the secret message before embedding to add another layer of security.

## Results and Graphs:

**Results:**

- Mean Squared Error (MSE): 1.4351374e-06

- Signal-to-Noise Ratio (SNR): 40.271172523498535 dB

- Cover Audio RMS: 0.12359625

- Stego Audio RMS: 0.12360499

**Graphs:**

**Cover, Secret and Stego Audio Waveform:**
![AudioWaveform](https://github.com/user-attachments/assets/8ebe1051-d438-4d0c-ba88-6ea22c06c738)

**Histogram Comparision:**
![Histogram](https://github.com/user-attachments/assets/65c830e3-6ba6-4b32-a70d-037065e3374e)

**Correlation between Cover and Stego Audio:**
![Correlation](https://github.com/user-attachments/assets/b3b6b0df-c129-452b-b708-65ca7de4ce23)

**RMS Energy Comparision:**
![RMSEnergy](https://github.com/user-attachments/assets/d46d3bc6-1a46-49d2-adfa-71af7e1794f2)

**Cover and Stego Audio Waveform:**
![CoverStegoWaveform](https://github.com/user-attachments/assets/01dd3b10-644c-4394-b0b9-d6bf5df01540)

## Conclusion

This project demonstrates the effective use of spread spectrum methodology for audio steganography, balancing imperceptibility, robustness, and security. By leveraging the principles of spread spectrum, the system can embed secret information within audio signals in a way that is resistant to noise, compression, and other common signal distortions, while remaining undetectable to human listeners.

The technique holds significant potential for applications in secure communication, digital watermarking, and covert data transmission. Its reliance on pseudo-random sequences ensures that unauthorized extraction is infeasible without the proper key, adding a critical layer of security.

Future enhancements, such as incorporating adaptive embedding and encryption, could further improve the system's performance and expand its applicability. This project serves as a robust foundation for exploring advanced steganographic techniques in the audio domain.

## License

This project is licensed under the MIT License. Feel free to use, modify, and distribute the code for academic and research purposes.
