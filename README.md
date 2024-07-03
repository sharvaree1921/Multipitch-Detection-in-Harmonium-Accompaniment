# Multipitch Detection in Harmonium Accompaniment
This project explores the possibility of tracking harmonium pitch accompaniment from Hindustani Vocal concerts. Accurate multpitch trajectory of harmonium helps in understanding the musical structures, interaction between vocal and harmonium pitches (synchrony) and overall improve musician performance practices. We rely on timbre-aware deep learning model for harmonium multipitch predictions from a Hindustani concert. The training data required for this DL model is Hindustani concert data with accurately labeled harmonium pitch values. Lack of availability of such type of dataset prompted us to make one. The dataset consists of:
1. Artificial polyphonic coherent and incoherent mixtures generated from individual closed mic recordings of harmonium and vocals taken from [1]
2. Multipitch annotations of harmonium-solo recordings done via SAUSNet algorithm [2]

## Project Organization
The project contains the following:
1. Harmonium-solo_recordings_with_annotations.zip: Compressed folder containing xx harmonium-solo recordings, organized raag-wise along with their annotated multipitch tracks
2. Octave_Notes.zip: Compressed folder containing recordings of 12 notes of the middle octave from the Harmonium of the musician (Jignesh)

## Harmonium Multipitch Dataset
The Harmonium Multipitch dataset is of a total duration of 3 hrs 42 min, containing harmonium-solo recordings of specific raagas with their multi-pitch annotations. These recordings
vary in duration between 35 sec to 2 mins, with the mean recording duration being 1 min 10 sec.

The North Indian Raga Performance OSF dataset[1] is a publicly available dataset containing audio-visual recordings of complete raga performances, mostly recorded in India and the UK. It consists of separate instrument stems recorded through an individual microphone termed as 'closed mic recordings'. We borrow harmonium-solo recordings from this dataset. Since some of these recordings had inherent bleed of other instruments, a professional harmonium player (Jignesh) was asked to play the harmonium accompaniment for those concerts. The process of getting harmonium-solo recordings from the player is as follows:
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

Coherent mixtures are prepared of raga performances by combining vocal-solo closed mic recordings from OSF dataset and harmonium accompaniment produced by Jignesh. Incoherent mixtures are prepared by combining vocal-solo and some other harmonium-solo closed mic recordings from OSF dataset. These mixtures are generated by mixing them at -5,-2.5,0,2.5 dB SNR values (-ve dB: Vocal dominant, +dB: Harmonium dominant). This makes the total duration of mixture dataset as 17 hr 45 mins. The smaller segments of audio from vocal-solo closed mic recordings from OSF vocal concerts along with their time stamps are mentioned in a text file with respective sections. Thus, for Kedar, Bhoop, Tilak Kamod and Multani ragas, we have their respective time stamps and their obtained multipitch ground values. For Jhinjhoti and Jaunpuri, we have 1.28 sec smaller segments along with their obtained multipitch ground values, since they were used for incoherent mixture preparation.

Following is the structure of dataset organized into the folders:

- **Harmonium-solo_recordings_with_annotations**
  - ArunBh_Kedar
    - Audios_Voc
      - ArunBh_Kedar_sec1.wav
      - ArunBh_Kedar_sec2.wav
      - ...
    - Audios_Har
      - ArunBh_Kedar_Har_sec1.wav
      - ArunBh_Kedar_Har_sec2.wav
      - ...
    - Pitches
      - ArunBh_Kedar_Har_sec1.csv
      - ArunBh_Kedar_Har_sec2.csv
      - ...
    - ArunBh_Kedar_time_stamps.txt
  - MAK_TilakK
  - ...

## References
1. Martin Clayton, Laura Leante, Simone Tarsitani (2019) North Indian Raga Performance:
OSF Dataset, DOI 10.17605/OSF.IO/NKJGZ
2. Weiß, Christof, and Geoffroy Peeters. ”Deep-Learning Architectures for Multi-Pitch Estima-
tion: Towards Reliable Evaluation.” arXiv preprint arXiv:2202.09198 (2022).
