## FunctionDef sorting(file)
**sorting**: The function of sorting is to categorize a file based on its extension.

**parameters**:
- file: A string representing the name of the file to be sorted.

**Code Description**:
The sorting function first creates a list of keys from the extensions dictionary. It then iterates over each key and its corresponding extensions. For each extension, it checks if the file name ends with that extension. If a match is found, the function returns the key associated with that extension.

**Note**:
- Make sure to provide the file name as a parameter in the function call.
- Ensure that the extensions dictionary is correctly defined before calling the sorting function.

**Output Example**:
If the file name is "document.pdf", the function may return "PDF" based on the extension mapping in the extensions dictionary.
