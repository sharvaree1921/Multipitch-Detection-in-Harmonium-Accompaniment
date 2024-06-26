# Multipitch Detection in Harmonium Accompaniment
This project explores the possibility of tracking harmonium pitch accompaniment from Hindustani Vocal concerts. Accurate multpitch trajectory of harmonium helps in understanding the musical structures, interaction between vocal and harmonium pitches (synchrony) and overall improve musician performance practices. We rely on timbre-aware deep learning model for harmonium multipitch predictions from a Hindustani concert. The training data required for this DL model is Hindustani concert data with accurately labeled harmonium pitch values. Lack of availability of such type of dataset prompted us to make one. The dataset consists of:
1. Artificial polyphonic coherent and incoherent mixtures generated from individual closed mic recordings of harmonium and vocals taken from []
2. Multipitch annotations of harmonium-solo recordings done via SAUSNet algorithm []

## Project Organization
The project contains the following:
1. Harmonium-solo_recordings_with_annotations.zip: Compressed folder containing xx harmonium-solo recordings, organized raag-wise along with their annotated multipitch tracks
2. Mixtures.zip: Compressed folder containing artificially generated xx coherent and xx incoherent mixtures used in this project with their corresponding harmonium accompaniment pitch tracks

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

| Soloist (Vocal) | Raag | Duration  | Source |
| ------------- | ------------- | ------------- | ------------- |
| Arun Bhaduri  | Kedar  | 26:12  | Harmonium Accompaniment by Jignesh  |
| Manjiri Asanare Kelkar  | Tilak Kamod  | 20:41  | Harmonium Accompaniment by Jignesh |
| Veena Sahasrabuddhe  | Bhoop  | 57:25 | Harmonium Accompaniment by Jignesh |
| Vijay Koparkar  | Multani  | 49:28  | Harmonium Accompaniment by Jignesh |
| Manjiri Asanare Kelkar  | Jaunpuri | 30:30 | Harmonium solo closed-mic recording from OSF |
| Manjiri Asanare Kelkar  | Jhinjhoti  | 27:46  | Harmonium solo closed-mic recording from OSF  |
 
## References
