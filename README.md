# Accent Normalization Study
A study on Accent removal in speech enhancement models: Benchmarking, Measuring, Interpreting, and Mitigating Accent Drift

This project studies how speech enhancement affects automatic speech recognition (ASR), especially under noisy conditions and for accented English speech. The goal is to evaluate whether enhancement improves transcription robustness or unintentionally degrades ASR performance by removing speech cues that are useful for recognition.

The experiment compares ASR outputs before and after applying speech enhancement across different noise types and signal-to-noise ratios (SNRs). It measures recognition quality using a small set of core metrics such as Word Error Rate (WER), change in WER after enhancement, and basic audio quality or degradation indicators. The project also includes provisions for listening to audio samples before and after enhancement so that quantitative results can be compared with perceptual observations.

Overall, the project is motivated by a safety and robustness question: speech enhancement systems are often treated as preprocessing tools that should help downstream models, but they may not affect all speakers or accents equally. By auditing this interaction, the project aims to identify when enhancement is beneficial, when it is harmful, and whether certain noise or accent conditions are more vulnerable to ASR degradation.

## First Experiment 

The notebook implements a matched-prompt ASR audit pipeline for accented speech. It loads CMU ARCTIC and L2-ARCTIC data, adds controlled noise, applies speech enhancement models, runs Whisper ASR, and evaluates WER/CER, degradation, helped/hurt rates, bootstrap confidence intervals, and summary plots. It also includes audio playback cells for checking samples before and after enhancement. The results have been consolidated in the PDF.

## Next Steps
- It seems like adding noise affects some languages more than the others and hence the speech enhancement results will be confounded based on that. Further experiments should be conducted in that regard.
- Mechanistic Interpretability experiments to see where the accent info resides in speech enhancement models.
