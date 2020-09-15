## Description

Lesion masks for the [PROSTATEx](https://wiki.cancerimagingarchive.net/display/Public/SPIE-AAPM-NCI+PROSTATEx+Challenges) prostate MRI dataset.
It comprises prostate MRI exams with PI-RADS score = 2+ lesions. These are classified as clinically significant or not. Only patients with PI-RADS score = 3+ lesions underwent biopsy and are collected in the PROSTATEx 2 dataset, together with the resulting bioptic lesion Gleason Grade.

The original dataset only provided lesion coordinates and an accompanying screenshot for each finding, with several issues due to misplaced coordinates or not clearly identifiable PI-RADS score = 2 lesions. This repository contains the result of a lesion-by-lesion quality check conducted at the [Department of Advanced Biomedical Sciences](http://www.dises.unina.it/en_GB/web/guest/-/768572-dipartimento-di-scienze-biomediche-avanzate) of the [University of Naples "Federico II"](http://www.unina.it/), in the form of lesion masks on axial T2-weighted and ADC images for all correctly identifiable findings in the PROSTATEx/PROSTATEx2 training dataset. As the ground truth was not available for the test sets, the same quality check was not performed on that data.

We encourage the use of this data for radiomics and machine learning investigations in magnetic resonance imaging for prostate cancer, appropriately referencing the repository. Quality checks on the provided masks or other improvements are also welcome as pull requests to the repository.

## Files

### Lesion masks

The files are in compressed NIFTI (.nii.gz) format and collected in separate folders for T2 and ADC images (n = 299 lesions). Each filename contains the following information (separated by underscores):

- "PROSTATEx Patient ID" + "Finding ID" + "Sequence name" + "ROI"

As sometimes multiple axial ADC/T2 image sequences are available for a patient, the repository also includes a list in CSV format containing the correct images for each mask. The list is structured as follows (separated by underscores):

- "PROSTATEx Patient ID" + "Sequence name" + "Sequence number"

The sequence number corresponds to the number at the beginning of the PROSTATEx dataset DICOM image folders for each patient.

Finally, the "PROSTATEx_classes.csv" file contains the ground truths for all lesions included in the dataset, obtained from the orignial PROSTATEx and PROSTATEx2 data. This file is structured as follows (separated by underscores):
- ID column = "PROSTATEx Patient ID" + "Finding ID"
- Clinically Significant column (i.e. Gleason Score > 3+3, Gleason Grade Group/ISUP score > 1) = "True"/"False"
- Gleason Grade Group/ISUP score column = "No Biopsy" or 1-5

Patients who were classified as PI-RADS score = 2 did not undergo biopsy and their lesions are always assumed to be not clinically significant.

Full exam DICOM files are retrievable through the Cancer Imaging Archive at: [https://wiki.cancerimagingarchive.net/display/Public/SPIE-AAPM-NCI+PROSTATEx+Challenges](https://wiki.cancerimagingarchive.net/display/Public/SPIE-AAPM-NCI+PROSTATEx+Challenges)

### Prostate and zonal anatomy masks

The files are in compressed NIFTI (.nii.gz) format, and all segmentations have been performed on axial T2 images (n = 204 exams). Each filename contains the following information (separated by underscores):

- "PROSTATEx Patient ID"

The masks included in the "mask_prostate" directory represent whole-gland masks (binarized). Those included in "mask_pz" and "mask_tz" are limited respectively to the peripheral and rest (transition zone, central zone, anterior stroma) of the gland, also binarized. The background always has a value of 0. All segmentations were performed manually and the masks underwent an automated cluster cleaning to remove eventual imperfections.

As sometimes multiple axial T2 image sequences are available for a patient, the repository also includes a list in CSV format containing the correct images for each mask. The list is structured as follows (separated by underscores):

- "PROSTATEx Patient ID" + "Sequence name" + "Sequence number"

The sequence number corresponds to the number at the beginning of the PROSTATEx dataset DICOM image folders for each patient.

Full exam DICOM files are retrievable through the Cancer Imaging Archive at: [https://wiki.cancerimagingarchive.net/display/Public/SPIE-AAPM-NCI+PROSTATEx+Challenges](https://wiki.cancerimagingarchive.net/display/Public/SPIE-AAPM-NCI+PROSTATEx+Challenges)

## License

Creative Commons Attribution 4.0 International (CC-BY-4.0). See "LICENSE" file for full details.
