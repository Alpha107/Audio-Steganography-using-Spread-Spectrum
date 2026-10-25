<h1 align="center">🎧 Audio Steganography · Spread Spectrum</h1>

<p align="center">Spread a secret message across the whole spectrum with a secret PN key — hard to hear, hard to find.</p>

<p align="center">
  <img src="https://img.shields.io/badge/method-DSSS-blueviolet" alt="DSSS">
  <img src="https://img.shields.io/badge/cover%20SNR-40.3%20dB-brightgreen" alt="SNR">
  <img src="https://img.shields.io/badge/repo-docs%20only-lightgrey" alt="Docs only">
</p>

<p align="center"><img src="https://github.com/user-attachments/assets/01dd3b10-644c-4394-b0b9-d6bf5df01540" width="760" alt="Cover vs stego waveform"></p>

> **Docs only.** Results and plots are from the original notebook, which isn't in this repo.
> [Details →](#status--known-issues)

## Result

| Metric (cover vs stego) | Value |
|---|---|
| **SNR** | **40.3 dB** (imperceptible) |
| **MSE** | 1.4 × 10⁻⁶ |

## How it works

```mermaid
flowchart LR
    M["Secret bits"] --> X["× PN sequence<br/>(shared key)"]
    X --> A["+ cover audio<br/>low amplitude, high band"]
    A --> S["Stego audio"]
    S --> D["Correlate with<br/>same PN → bits"]
```

**Why DSSS:** low probability of detection, tolerance to noise, and no extraction without the PN key.

<table>
  <tr>
    <td width="50%"><img src="https://github.com/user-attachments/assets/b3b6b0df-c129-452b-b708-65ca7de4ce23" alt="Correlation"><br><sub>Cover vs stego correlation</sub></td>
    <td width="50%"><img src="https://github.com/user-attachments/assets/d46d3bc6-1a46-49d2-adfa-71af7e1794f2" alt="RMS energy"><br><sub>RMS energy</sub></td>
  </tr>
</table>

## Status & known issues

| Issue | Effect |
|---|---|
| **No code in the repo** | Results can't be reproduced from here |
| Bit-error rate (BER) not reported | Recovery accuracy is unknown |
| High-band embedding | MP3 compression strips high frequencies and can destroy the message |
| Robustness vs imperceptibility | A stronger signal is easier to recover but more audible |

## Roadmap

- [ ] Upload the notebook and sample audio
- [ ] Report BER, with error-correcting codes (Hamming / Reed–Solomon)
- [ ] MP3, noise and resampling attack tests
