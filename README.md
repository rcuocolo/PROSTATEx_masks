# PROSTATEx masks

## Introduction

Lesion masks for the [PROSTATEx dataset](https://wiki.cancerimagingarchive.net/display/Public/SPIE-AAPM-NCI+PROSTATEx+Challenges).
The PROSTATEx dataset comprises prostate MRI exams with PI-RADS score = 2+ lesions. These are classified as clinically significant or not. Only PI-RADS score = 3+ underwent biopsy and are collected in the PROSTATEx 2 dataset, together with the resulting bioptic lesion Gleason Grade.

The original dataset only provided lesion coordinates and an accompanying screenshot for each finding, with several issues due to misplaced coordinates or not clearly identifiable PI-RADS score = 2 lesions. This repository contains the result of a lesion-by-lesion quality check conducted at the Department of Advanced Biomedical Sciences of the University of Naples "Federico II", in the form of lesion masks on axial T2-weighted and ADC images for all correctly identifiable findings in the PROSTATEx/PROSTATEx2 training dataset. As the ground truth was not available for the test sets, the same quality check was not performed on that data.

We encourage the use of this data for radiomics and machine learning investigations in magnetic resonance imaging for prostate cancer, appropriately referencing the repository. Quality checks on the provided masks or other improvements are also welcome as pull requests to the repository.

## Files

The files are in compressed NIFTI (.nii.gz) format and collected in separate folders for T2 and ADC images. Each filename contains the following information (separated by underscores):

- "PROSTATEx Patient ID" + "Finding ID" + "Sequence name" + "ROI"

As sometimes multiple axial ADC/T2 image sequences are available for a patient, the repository also includes a list in CSV format containing the correct images for each mask. The list is structured as follows (separated by underscores):

- "PROSTATEx Patient ID" + "Sequence name" + "Sequence number"

The sequence number corresponds to the number at the beginning of the PROSTATEx dataset DICOM image folders for each patient.

## License

Creative Commons Attribution 4.0 International (CC-BY-4.0). See "LICENSE" file for full details.
