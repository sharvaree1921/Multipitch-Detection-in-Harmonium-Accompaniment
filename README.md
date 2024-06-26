# Multipitch Detection in Harmonium Accompaniment
This project explores the possibility of tracking harmonium pitch accompaniment from Hindustani Vocal concerts. Accurate multpitch trajectory of harmonium helps in understanding the musical structures, interaction between vocal and harmonium pitches (synchrony) and overall improve musician performance practices. We rely on timbre-aware deep learning model for harmonium multipitch predictions from a Hindustani concert. The training data required for this DL model is Hindustani concert data with accurately labeled harmonium pitch values. Lack of availability of such type of dataset prompted us to make one. The dataset consists of:
1. Artificial polyphonic coherent and incoherent mixtures generated from individual closed mic recordings of harmonium and vocals taken from [1]
2. Multipitch annotations of harmonium-solo recordings done via SAUSNet algorithm [2]

## Project Organization
The project contains the following:
1. Harmonium-solo_recordings_with_annotations.zip: Compressed folder containing xx harmonium-solo recordings, organized raag-wise along with their annotated multipitch tracks
2. Mixtures_with_annotations.zip: Compressed folder containing artificially generated xx coherent and xx incoherent mixtures used in this project with their corresponding harmonium accompaniment pitch tracks

## Harmonium Multipitch Dataset
The Harmonium Multipitch dataset is of a total duration of 3 hrs 42 min, containing harmonium-solo recordings of specific raagas with their multi-pitch annotations. These recordings
vary in duration between 35 sec to 2 mins, with the mean recording duration being 1 min 10 sec.

The North Indian Raga Performance OSF dataset[] is a publicly available dataset containing audio-visual recordings of complete raga performances, mostly recorded in India and the UK. It consists of separate instrument stems recorded through an individual microphone termed as 'closed mic recordings'. We borrow harmonium-solo recordings from this dataset. Since some of these recordings had inherent bleed of other instruments, a professional harmonium player (Jignesh) was asked to play the harmonium accompaniment for those concerts. The process of getting harmonium-solo recordings from the player is as follows:
1. Created smaller chunks of audio from vocal-solo closed mic recordings from OSF vocal concerts
2. Asked a professional harmonium player (Jignesh) to play accompaniment harmonium by:
  a. First listening to the original concert and vocal-solo chunks 
  b. Familiarizing to scale, singer improvisations to raag
  c. Using headphones to listen to vocal-solo segments and simultaneously play the supporting accompaniment on his harmonium
3. Obtained harmonium solo recordings corresponding to each vocal-solo chunk

The following table shows the sourcing of harmonium-solo recordings used in this project:

| Code | Soloist (Vocal) | Raag | Duration  | Source | Link to Concert Audio |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ArunBh_Kedar | Arun Bhaduri  | Kedar  | 26:12  | Harmonium Accompaniment by Jignesh  | [ArunBh_Kedar_Steremix.wav](https://osf.io/mauzt) |
| MAK_TilakK | Manjiri Asanare Kelkar  | Tilak Kamod  | 20:41  | Harmonium Accompaniment by Jignesh | [MAK_TilakK_Stereomix.wav](https://osf.io/n5qkc) |
| VS_Bhoop | Veena Sahasrabuddhe  | Bhoop  | 57:25 | Harmonium Accompaniment by Jignesh | [VS_Bhoop_Stereomix.wav](https://osf.io/9ags7) |
| VK_Multani | Vijay Koparkar  | Multani  | 49:28  | Harmonium Accompaniment by Jignesh | [VK_Multani_Stereomix.wav](https://osf.io/k45q2) |
| MAK_Jaun | Manjiri Asanare Kelkar  | Jaunpuri | 30:30 | Harmonium solo closed-mic recording from OSF | [MAK_Jaun_Stereomix.wav](https://osf.io/prjq4) |
| MAK_Jhin | Manjiri Asanare Kelkar  | Jhinjhoti  | 27:46  | Harmonium solo closed-mic recording from OSF  | [MAK_Jhin_Stereomix.wav](https://osf.io/dxv76) |


- **Harmonium-solo_recordings_with_annotations**
  - ArunBh_Kedar
    - Audios
      - ArunBh_Kedar_sec1.wav
      - ArunBh_Kedar_sec2.wav
      - ...
    - Pitches
      - ArunBh_Kedar_Har_sec1.csv
      - ArunBh_Kedar_Har_sec2.csv
      - ...
  - MAK_TilakK
    - Audios
      - MAK_TilakK_sec1.wav
      - MAK_TilakK_sec2.wav
      - ...
    - Pitches
      - MAK_TilakK_Har_sec1.csv
      - MAK_TilakK_Har_sec2.csv
      - ...
  - ...
  - **Mixtures_with_annotations**
    - Coherent Mixtures
      - ArunnBh_Kedar
        - Mixtures
          - ArunnBh_Kedar_mix1_-5.wav
          - ArunnBh_Kedar_mix1_-2.5.wav
          - ArunnBh_Kedar_mix1_0.wav
          - ArunnBh_Kedar_mix1_2.5.wav
          - ArunnBh_Kedar_mix2_-5.wav
          - ... 
        - Pitches
          - ArunnBh_Kedar_mix1_GT_-5.csv
          - ArunnBh_Kedar_mix1_GT_-2.5.csv
          - ArunnBh_Kedar_mix1_GT_0.csv
          - ArunnBh_Kedar_mix1_GT_2.5.csv
          - ArunnBh_Kedar_mix2_GT_-5.csv
      - MAK-TilakK
      - ...
    - Incoherent Mixtures
    -   Mixtures
    -   Pitches
 

## References
1. Martin Clayton, Laura Leante, Simone Tarsitani (2019) North Indian Raga Performance:
OSF Dataset, DOI 10.17605/OSF.IO/NKJGZ
2. Weiß, Christof, and Geoffroy Peeters. ”Deep-Learning Architectures for Multi-Pitch Estima-
tion: Towards Reliable Evaluation.” arXiv preprint arXiv:2202.09198 (2022).
