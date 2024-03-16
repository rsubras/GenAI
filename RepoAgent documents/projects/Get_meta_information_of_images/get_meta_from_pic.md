## FunctionDef get_exif(image)
**get_exif**: The function of get_exif is to retrieve the Exchangeable image file format (EXIF) metadata from an image.

**parameters**:
- image: The image object from which the EXIF metadata needs to be extracted.

**Code Description**:
The get_exif function first verifies the image and then retrieves the EXIF metadata using the _getexif method of the image object.

**Note**:
It is important to ensure that the input image is valid and can be verified before calling this function to avoid any errors.

**Output Example**:
{
    'ExifVersion': b'0220',
    'ShutterSpeedValue': (4173856, 1000000),
    'DateTimeOriginal': '2022:01:01 12:00:00',
    ...
}
## FunctionDef get_labeled_exif(exif)
**get_labeled_exif**: The function of get_labeled_exif is to map the keys of the input dictionary 'exif' to their corresponding values in the TAGS dictionary and return a new dictionary with the mapped key-value pairs.

**parameters**:
- exif: A dictionary containing the metadata information of an image.

**Code Description**:
The get_labeled_exif function iterates over the key-value pairs in the input 'exif' dictionary. For each key, it uses the TAGS dictionary to retrieve the corresponding value and assigns it to the new 'labeled' dictionary. Finally, it returns the 'labeled' dictionary containing the mapped key-value pairs.

**Note**:
- The TAGS dictionary is assumed to be defined elsewhere in the code.
- It is important to ensure that the keys in the 'exif' dictionary are compatible with the keys in the TAGS dictionary for proper mapping.

**Output Example**:
If the input 'exif' dictionary is {'ExposureTime': '1/1000', 'FNumber': 'f/2.8'}, the function may return {'ExposureTime': '1/1000', 'FNumber': 'f/2.8'} after mapping the keys using the TAGS dictionary.
