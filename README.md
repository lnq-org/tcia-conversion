# tcia-conversion
Scripts for converting TCIA CT-Lymph-Node dataset to dicom

Collection is here: https://wiki.cancerimagingarchive.net/display/Public/CT+Lymph+Nodes

Goal: convert masks for use as training set.

Status:
* Source CT data is in DICOM
* Masks (volumetric segmentations) exist in nifti format
* Some additional annotations are in MITK format

Conversion ideas:
* Convert all masks to DICOM SEG linked to corresponding series
* Load full collection into dedicated Google DICOM store for viewing in OHIF or Slicer
* Use dcmqi to do the nifti to dicom conversion
* Re-export the CTs with better window/level settings and experiment with compression
* Create MRB files preloaded with segmentations

Open issues:
* What colors should we use so the seg outlines are easily visible
* What naming conventions should we use in the SEG (picking the right dicom terminology)
* What anatomy labels should we use and can we determine them automatically, or do we need to manually assign them
* Are there smoothness or other geometric constratints we can apply to clean up the segmentations
