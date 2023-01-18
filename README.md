## About

This is a simple DICOM to NIfTI validator script and dataset based on Siemens XA30 DICOM images.

Siemens notes that XA30 systems can export DICOMs in one of two modes:

* Interoperability: assures that the data is compatible to any DICOM node, but enhanced features cannot be guaranteed.

* Enhanced: preserves the enhanced features of the source images.

This repository contains data saved in Interoperability mode, see [https://github.com/neurolabusc/dcm_qa_xa30](https://github.com/neurolabusc/dcm_qa_xa30) for Enhanced mode data. An identical acquisition will populate different tags depending on whether Interoperability or Enhanced mode is selected. The table below highlights differences from dcm2niix's perspective:

| BIDS field          | Interoperability         | Enhanced                 |
| ------------------- | ------------------------ | ------------------------ |
| ImagingFrequency    | 0018,0084                | 0018,9098                |
| PhaseEncodingSteps  | 0018,0089                | 0018,9231                |
| SAR                 | 0018,1316                | 0018,9181                |
| MTState             | ?                        | 0018,9020                |
| AcquisitionDuration | ?                        | 0018,9073                |

## Details

Images were acquired by Hu Cheng, Isaiah Innis, and Daniel Levitas using a Siemens Prisma Fit running XA30 at Indiana University. Additional sequence details are provided in the included PDF-format file.

* Common Parameters 
  * Manufacturer: Siemens
  * Model: Prisma Fit
  * Software Versions: MR XA30

| Series | Sequence name            |
| ------ | ------------------------ |
| 5-6    | anat-T1w_acq-tfl         |
| 7-8    | func-bold_task-fa_run-1  |
| 9-10   | gre_field_mapping        |
| 11-17  | DWI_dir80_PA             |
| 18-20  | asl_2d_tra               |

## Running

Assuming that the executable dcm2niix is in your path, you should be able to simply run the script `batch.sh` from the terminal.
