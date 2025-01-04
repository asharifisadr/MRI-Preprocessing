
# **ADNI NIfTI Preprocessing Pipeline**

This repository contains a Python script for preprocessing NIfTI-format brain MRI images from the Alzheimer's Disease Neuroimaging Initiative (ADNI) dataset. The preprocessing pipeline includes bias field correction, skull stripping, registration to MNI space, and intensity normalization. This script is designed to streamline the preprocessing of neuroimaging data for downstream analysis.

---

## **Features**
- **Batch Processing**: Automatically processes multiple `.nii.gz` files from a specified input directory.
- **Bias Field Correction**: Reduces intensity inhomogeneity using N4ITK bias field correction.
- **Skull Stripping**: Removes non-brain tissues from MRI scans using `antspynet` brain extraction.
- **Registration to MNI Space**: Aligns MRI images to the standard MNI template for consistency across datasets.
- **Intensity Normalization**: Scales voxel intensities to the range [0, 1].

---

## **Dependencies**
Ensure the following Python libraries are installed:
- `os`
- `nibabel`
- `ants`
- `numpy`
- `matplotlib`
- `google.colab` (if running in Google Colab)
- `antspynet`

Install dependencies using pip:  
```bash
pip install nibabel antspyx antspynet
```

---

## **Setup**
1. Mount your Google Drive (if using Google Colab).  
   Uncomment the following line in the code:  
   ```python
   drive.mount('/content/drive')
   ```

2. Update the paths for your **input folder** and **output folder** in the script:
   ```python
   input_folder = '/content/drive/MyDrive/ADNI_BASE_NIfTI'
   output_folder = '/content/drive/MyDrive/ADNI_Preprocessed'
   ```

3. Ensure your input folder contains `.nii.gz` files (NIfTI images).

---

## **Usage**
1. Run the script in your Python environment or Google Colab.
2. The script will process files in the input folder that have not yet been processed and save the preprocessed files to the output folder.

### **Steps Performed**
1. **Bias Field Correction**: Reduces intensity inconsistencies.
2. **Skull Stripping**: Extracts brain regions from the MRI images.
3. **Registration**: Aligns images to the MNI template using affine transformation.
4. **Normalization**: Scales voxel intensities for standardization.

---

## **Output**
- Preprocessed files are saved in the output folder with the suffix `_preprocessed.nii.gz`.
- Skipped files (already processed) are logged in the console.

---

## **Example Console Output**
```plaintext
Skipping already processed file: subject1_preprocessed.nii.gz
Processing file: /content/drive/MyDrive/ADNI_BASE_NIfTI/subject2.nii.gz
Applying N4 bias field correction...
Performing skull stripping...
Registering to MNI space...
Normalizing intensities...
Saved preprocessed file to: /content/drive/MyDrive/ADNI_Preprocessed/subject2_preprocessed.nii.gz
All files have been processed and saved!
```

---

## **Contributing**
Feel free to fork this repository and submit pull requests for improvements or additional features.  

