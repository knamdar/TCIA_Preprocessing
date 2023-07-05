TCIA DICOM to NIfTI Converter

This script is designed to convert DICOM files from the Cancer Imaging Archive (TCIA) into NIfTI format. It is implemented in Python and uses the PyDICOM, NumPy, and NiBabel libraries to process the images.

In addition to converting the image data, the script also renames directories based on certain DICOM tags. Specifically, it renames study directories based on the Modality and StudyDescription DICOM tags, and series directories based on the SeriesDescription DICOM tag.
Installation

Before running the script, you must install its dependencies. You can do so by running:

pip install numpy pydicom nibabel

Usage

To use the script, you need to specify the root directory for your patient data and the output directory where you want to save the processed data. These are specified in the root_dir and output_dir variables at the bottom of the script.

python

# Root directory for your patient data
root_dir = "path_to_your_root_dir"
# Destination directory
output_dir = "path_to_your_output_dir"

After setting these variables, you can simply run the script using a Python interpreter:

python script.py

Directory Renaming

The script renames study and series directories according to specific DICOM tags:

    Study directories are renamed based on the Modality and StudyDescription DICOM tags. The new name is formed as <Modality>_<StudyDescription>.
    Series directories are renamed based on the SeriesDescription DICOM tag.

If a DICOM tag is not found or the directory is not a study or series directory, the original name will be preserved.
Error Logging

The script includes error logging functionality. If it encounters an error while processing a DICOM series (for example, due to inconsistent slice shapes), it will skip that series and log the error in a file named log.txt in the current directory.
Contributing

Contributions are welcome! Please submit a pull request or create an issue to propose changes or additions.
License

This project is licensed under the terms of the MIT license.
