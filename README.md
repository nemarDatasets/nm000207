# Class for Kojima2024B dataset management. P300 dataset

Class for Kojima2024B dataset management. P300 dataset.

## Dataset Overview

- **Code**: Kojima2024B
- **Paradigm**: p300
- **DOI**: 10.7910/DVN/1UJDV6
- **Subjects**: 15
- **Sessions per subject**: 1
- **Events**: Target=[111, 112, 113, 114], NonTarget=[101, 102, 103, 104]
- **Trial interval**: [-0.5, 1.2] s
- **Runs per session**: 12
- **File format**: BrainVision
- **Number of contributing labs**: 1

## Acquisition

- **Sampling rate**: 1000.0 Hz
- **Number of channels**: 64
- **Channel types**: eeg=64, eog=2
- **Channel names**: AF3, AF4, AF7, AF8, AFz, C1, C2, C3, C4, C5, C6, CP1, CP2, CP3, CP4, CP5, CP6, CPz, Cz, F1, F2, F3, F4, F5, F6, F7, F8, FC1, FC2, FC3, FC4, FC5, FC6, FCz, FT10, FT7, FT8, FT9, Fp1, Fp2, Fz, O1, O2, Oz, P1, P2, P3, P4, P5, P6, P7, P8, PO3, PO4, PO7, PO8, POz, Pz, T7, T8, TP10, TP7, TP8, TP9, hEOG, vEOG
- **Montage**: standard_1020
- **Hardware**: BrainAmp
- **Reference**: right mastoid
- **Ground**: left mastoid
- **Sensor type**: EEG
- **Line frequency**: 50.0 Hz
- **Cap manufacturer**: EasyCap
- **Electrode type**: passive Ag/AgCl
- **Electrode material**: Ag/AgCl
- **Auxiliary channels**: EOG (2 ch, vertical, horizontal)

## Participants

- **Number of subjects**: 15
- **Health status**: healthy
- **Age**: mean=22.8, min=21.0, max=24.0
- **Gender distribution**: male=13, female=2
- **Species**: human

## Experimental Protocol

- **Paradigm**: p300
- **Task type**: auditory stream segregation with oddball
- **Number of classes**: 2
- **Class labels**: Target, NonTarget
- **Trial duration**: 90.0 s
- **Tasks**: ASME-4stream, ASME-2stream
- **Study design**: within-subject comparison
- **Study domain**: auditory BCI
- **Feedback type**: none
- **Stimulus type**: auditory tones
- **Stimulus modalities**: auditory
- **Primary modality**: auditory
- **Synchronicity**: synchronous
- **Mode**: offline
- **Training/test split**: False
- **Instructions**: focus selectively on deviant stimuli in one of the streams and count target deviant stimuli

## HED Event Annotations

Schema: HED 8.4.0 | Browse: https://www.hedtags.org/hed-schema-browser

```
  Target
    ├─ Sensory-event
    ├─ Experimental-stimulus
    ├─ Visual-presentation
    └─ Target

  NonTarget
    ├─ Sensory-event
    ├─ Experimental-stimulus
    ├─ Visual-presentation
    └─ Non-target

```
## Paradigm-Specific Parameters

- **Detected paradigm**: p300
- **Number of targets**: 4
- **Number of repetitions**: 15
- **Stimulus onset asynchrony**: {'ASME-4stream_overall': 150.0, 'ASME-2stream_overall': 300.0, 'within_stream': 600.0} ms

## Data Structure

- **Trials**: {'ASME-4stream': '600 stimuli per trial (4 trials per run, 6 runs)', 'ASME-2stream': '300 stimuli per trial (4 trials per run, 6 runs)'}
- **Blocks per session**: 12
- **Block duration**: 90.0 s
- **Trials context**: 12 runs alternating between ASME-4stream and ASME-2stream, 4 trials per run

## Preprocessing

- **Data state**: raw
- **Preprocessing applied**: False

## Signal Processing

- **Classifiers**: Linear Discriminant Analysis (LDA), shrinkage-LDA
- **Feature extraction**: mean amplitudes in 10 intervals (0.1s non-overlapping, 0-1.0s)
- **Frequency bands**: analyzed=[0.1, 8.0] Hz

## Cross-Validation

- **Method**: 3-fold chronological cross-validation (BCI simulation); 4-fold chronological cross-validation (binary classification)
- **Evaluation type**: offline simulation

## Performance (Original Study)

- **Asme-4Stream Accuracy**: 0.83
- **Asme-2Stream Accuracy**: 0.86

## BCI Application

- **Applications**: communication
- **Environment**: laboratory
- **Online feedback**: False

## Tags

- **Pathology**: Healthy
- **Modality**: auditory
- **Type**: ERP, P300

## Documentation

- **Description**: Four-class ASME BCI investigation comparing two strategies for multiclassing: ASME-4stream (four streams with single target stimulus each) vs ASME-2stream (two streams with two target stimuli each)
- **DOI**: 10.3389/fnhum.2024.1461960
- **Associated paper DOI**: 10.3389/fnhum.2024.1461960
- **License**: CC0-1.0
- **Investigators**: Simon Kojima, Shin'ichiro Kanoh
- **Senior author**: Shin'ichiro Kanoh
- **Contact**: simon.kojima@ieee.org
- **Institution**: Shibaura Institute of Technology
- **Department**: Graduate School of Engineering and Science (Simon Kojima); College of Engineering (Shin'ichiro Kanoh)
- **Address**: Tokyo, Japan
- **Country**: JP
- **Repository**: Harvard dataverse
- **Data URL**: https://doi.org/10.7910/DVN/1UJDV6
- **Publication year**: 2024
- **Funding**: JSPS KAKENHI (Grant Number JP23K11811 to Shin'ichiro Kanoh)
- **Ethics approval**: Review Board on Bioengineering Research Ethics of the Shibaura Institute of Technology
- **Keywords**: brain-computer interface, electroencephalogram, event-related potential, auditory scene analysis, stream segregation, machine learning, NASA-TLX

## Abstract

The ASME (Auditory Stream segregation Multiclass ERP) paradigm is used for an auditory brain-computer interface (BCI). Two approaches for achieving four-class ASME were investigated: ASME-4stream (four streams with a single target stimulus each) and ASME-2stream (two streams with two target stimuli each). Fifteen healthy subjects participated. ERPs were analyzed, and binary classification and BCI simulation were conducted offline using linear discriminant analysis. Average accuracies were 0.83 (ASME-4stream) and 0.86 (ASME-2stream). The ASME-2stream paradigm showed shorter latency and larger amplitude of P300, higher binary classification accuracy, and smaller workload. Both paradigms achieved sufficiently high accuracy (over 80%) for practical auditory BCI.

## Methodology

Subjects performed 12 runs alternating between ASME-4stream and ASME-2stream paradigms. Each run contained 4 trials with ~90s duration. ASME-4stream presented 4 streams (SOA=0.15s, 600 stimuli/trial, ratio 9:1 standard:deviant). ASME-2stream presented 2 streams with 2 deviant stimuli each (SOA=0.3s, 300 stimuli/trial, ratio 8:1:1). EEG recorded at 1000 Hz from 64 channels. EOG artifacts removed using ICA on 15 PCs. Data filtered (1-40 Hz for ERP, 0.1-8 Hz for classification), epoched (-0.1 to 1.2s), downsampled to 250 Hz. Classification used shrinkage-LDA with mean amplitudes from 10 intervals (0-1.0s) as features. Performance evaluated using 4-fold chronological cross-validation. Usability assessed via NASA-TLX questionnaire.

## References

Kojima, S. (2024). Replication Data for: Four-class ASME BCI: investigation of the feasibility and comparison of two strategies for multiclassing. Harvard Dataverse, V1. DOI: https://doi.org/10.7910/DVN/1UJDV6

Kojima, S. & Kanoh, S. (2024). Four-class ASME BCI: investigation of the feasibility and comparison of two strategies for multiclassing. Frontiers in Human Neuroscience 18:1461960. DOI: https://doi.org/10.3389/fnhum.2024.1461960
Appelhoff, S., Sanderson, M., Brooks, T., Vliet, M., Quentin, R., Holdgraf, C., Chaumon, M., Mikulan, E., Tavabi, K., Hochenberger, R., Welke, D., Brunner, C., Rockhill, A., Larson, E., Gramfort, A. and Jas, M. (2019). MNE-BIDS: Organizing electrophysiological data into the BIDS format and facilitating their analysis. Journal of Open Source Software 4: (1896). https://doi.org/10.21105/joss.01896

Pernet, C. R., Appelhoff, S., Gorgolewski, K. J., Flandin, G., Phillips, C., Delorme, A., Oostenveld, R. (2019). EEG-BIDS, an extension to the brain imaging data structure for electroencephalography. Scientific Data, 6, 103. https://doi.org/10.1038/s41597-019-0104-8

---
Generated by MOABB 1.5.0 (Mother of All BCI Benchmarks)
https://github.com/NeuroTechX/moabb
