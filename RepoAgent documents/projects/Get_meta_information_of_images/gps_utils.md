## FunctionDef format_lati_long(data)
**format_lati_long**: The function of format_lati_long is to convert latitude or longitude coordinates from degrees, minutes, and seconds format to decimal degrees.

**parameters**:
- data: A string representing the latitude or longitude coordinates in the format '[degrees, minutes, seconds]'.

**Code Description**:
The format_lati_long function takes a string input representing latitude or longitude coordinates in the format '[degrees, minutes, seconds]'. It processes the input, converts the coordinates to decimal degrees, and returns the result. The function first removes any brackets and splits the input string into a list. It then calculates the decimal degrees by converting degrees, minutes, and seconds to the corresponding values and summing them up. If the input contains seconds in the form of a fraction, it handles the conversion accordingly.

This function is utilized in the get_location function defined in gps_utils.py. In get_location, the format_lati_long function is called to convert the GPS latitude and longitude coordinates extracted from image metadata to decimal degrees. These decimal degree coordinates are then used to retrieve the address information using a geolocation service.

**Note**:
- Ensure that the input data follows the specified format '[degrees, minutes, seconds]' for accurate conversion.
- The function assumes that the input coordinates are in the correct format and may not handle all possible edge cases.

**Output Example**:
If the input latitude coordinates are '[37, 45, 30]', the function would return the decimal degree value 37.75833333333333.
## FunctionDef get_location(filename)
**get_location**: The function of get_location is to retrieve the address information based on the GPS latitude and longitude coordinates extracted from image metadata.

**parameters**:
- filename: A string representing the path to the image file from which GPS coordinates are extracted.

**Code Description**:
The get_location function takes the filename of an image as input. It processes the image file to extract the GPS latitude and longitude coordinates using the exifread library. These coordinates are then converted to decimal degrees by calling the format_lati_long function. Subsequently, the function uses the Nominatim geolocation service to reverse geocode the decimal degree coordinates and obtain the corresponding address information. Finally, the function returns the address associated with the provided GPS coordinates.

The format_lati_long function is crucial in this process as it handles the conversion of the GPS coordinates to decimal degrees, enabling accurate reverse geocoding. The get_location function relies on the accurate conversion provided by format_lati_long to obtain precise address information from the geolocation service.

**Note**:
- It is essential to ensure that the image file contains GPS metadata with valid latitude and longitude coordinates for the function to work correctly.
- The user_agent parameter in the Nominatim initialization should be set to a valid value to comply with the service's usage policy.

**Output Example**:
If the GPS coordinates extracted from the image correspond to a location in New York, the function would return "New York, USA" as the address.
