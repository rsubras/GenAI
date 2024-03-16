## ClassDef Bill_App
**Bill_App**: The function of Bill_App is to create a billing software application. 

**attributes**: The attributes of this Class.
- root: The root window of the application.
- sanitizer: The quantity of sanitizers.
- mask: The quantity of masks.
- hand_gloves: The quantity of hand gloves.
- dettol: The quantity of dettol.
- newsprin: The quantity of newsprin.
- thermal_gun: The quantity of thermal guns.
- rice: The quantity of rice.
- food_oil: The quantity of food oil.
- wheat: The quantity of wheat.
- daal: The quantity of daal.
- flour: The quantity of flour.
- maggi: The quantity of maggi.
- sprite: The quantity of sprite.
- limka: The quantity of limka.
- mazza: The quantity of mazza.
- coke: The quantity of coke.
- fanta: The quantity of fanta.
- mountain_duo: The quantity of mountain duo.
- medical_price: The total price of medical products.
- grocery_price: The total price of grocery items.
- cold_drinks_price: The total price of cold drinks.
- c_name: The name of the customer.
- c_phone: The phone number of the customer.
- bill_no: The bill number.
- search_bill: The bill number to search for.
- medical_tax: The tax amount for medical products.
- grocery_tax: The tax amount for grocery items.
- cold_drinks_tax: The tax amount for cold drinks.

**Code Description**: The Bill_App class is responsible for creating a billing software application. It initializes the root window and sets its properties. It also defines various variables to store the quantities of different products, prices, customer details, and tax amounts. The class contains methods for calculating the total price of different product categories, generating the bill, saving the bill, finding a bill, clearing the data, and exiting the application.

The class has a constructor method (__init__) that takes the root window as a parameter and initializes the attributes. It sets the size and title of the root window and creates a label for the title of the application. It also creates variables to store the quantities of different products, prices, customer details, and tax amounts.

The class has a total method that calculates the total price of medical products, grocery items, and cold drinks. It sets the values of the medical_price, grocery_price, and cold_drinks_price attributes. It also calculates the tax amounts for medical products, grocery items, and cold drinks and sets the values of the medical_tax, grocery_tax, and cold_drinks_tax attributes. Finally, it calculates the total bill amount by summing up the total prices and tax amounts.

The class has a welcome_bill method that displays a welcome message and the customer details in the bill area.

The class has a bill_area method that checks if the customer details are provided and if any products are purchased. If so, it displays the purchased products and their quantities and prices in the bill area. It also displays the tax amounts and the total bill amount.

The class has a save_bill method that prompts the user to save the bill and writes the bill data to a file.

The class has a find_bill method that searches for a bill based on the bill number and displays the bill data in the bill area.

The class has a clear_data method that prompts the user to confirm clearing the data and resets the quantities and attributes to their initial values.

The class has an exit_app method that prompts the user to confirm exiting the application and closes the root window.

**Note**: This class is part of a billing software application and is responsible for managing the GUI and calculations related to billing. It provides methods for generating bills, saving bills, searching for bills, and managing customer and product data.

**Output Example**: A bill is generated with the customer details, purchased products, quantities, prices, tax amounts, and the total bill amount displayed in the bill area. The bill can be saved and searched for using the bill number. The data can be cleared, and the application can be exited.
### FunctionDef __init__(self, root)
**__init__**: The function of __init__ is to initialize the Billing Software application and set up the initial state of the GUI.

**parameters**:
- self: The instance of the class.
- root: The root window of the application.

**Code Description**:
The `__init__` function is responsible for initializing the Billing Software application and setting up the initial state of the GUI. It takes the `self` parameter, which represents the instance of the class, and the `root` parameter, which is the root window of the application.

In this function, the `root` window is configured with a specific size and title using the `geometry` and `title` methods. The background color of the GUI is set to "#badc57".

Next, a label named "title" is created and added to the `root` window. This label displays the text "Billing Software" with a specific font, size, and style. It is placed at the top of the window and fills the entire width.

After that, various variables are initialized using the `IntVar` and `StringVar` classes. These variables are used to store the quantities of different items selected by the customer, the total prices of different categories of items, customer details, bill number, and tax amounts.

The customer details section is created using the `LabelFrame` widget and contains labels and entry fields for the customer name, phone number, and bill number. It also includes a search button to find a specific bill.

The medical items, grocery items, and cold drinks sections are created using the `LabelFrame` widget. Each section contains labels and entry fields for the respective items and their quantities.

The bill area is created using the `Frame` widget and includes a title label and a text area for displaying the bill details. A scrollbar is added to the text area to enable scrolling.

The button frame is created using the `LabelFrame` widget and contains buttons for performing various actions such as calculating the total, generating the bill, clearing the data, and exiting the application.

Finally, the `welcome_bill` function is called to display the welcome message and customer details in the text area.

**Note**: This function is called when the Billing Software application is initialized. It sets up the initial state of the GUI and prepares it for user interaction.
***
### FunctionDef total(self)
**total**: The function of total is to calculate the total bill amount for the customer. 

**parameters**:
- None

**Code Description**:
The `total` function is responsible for calculating the total bill amount for the customer. It performs various calculations based on the quantities of different items selected by the customer and updates the corresponding variables and labels to display the calculated values.

First, the function calculates the total price for the medical items by multiplying the quantity of each item with its respective price. The prices of the medical items are as follows:
- Hand Gloves: Rs. 12 per unit
- Sanitizer: Rs. 2 per unit
- Mask: Rs. 5 per unit
- Dettol: Rs. 30 per unit
- Newsprin: Rs. 5 per unit
- Thermal Gun: Rs. 15 per unit

The total price for the medical items is stored in the `total_medical_price` variable.

Next, the function calculates the total price for the grocery items by multiplying the quantity of each item with its respective price. The prices of the grocery items are as follows:
- Rice: Rs. 10 per unit
- Food Oil: Rs. 10 per unit
- Wheat: Rs. 10 per unit
- Daal: Rs. 6 per unit
- Flour: Rs. 8 per unit
- Maggi: Rs. 5 per unit

The total price for the grocery items is stored in the `total_grocery_price` variable.

Similarly, the function calculates the total price for the cold drinks by multiplying the quantity of each item with its respective price. The prices of the cold drinks are as follows:
- Sprite: Rs. 10 per unit
- Limka: Rs. 10 per unit
- Mazza: Rs. 10 per unit
- Coke: Rs. 10 per unit
- Fanta: Rs. 10 per unit
- Mountain Duo: Rs. 10 per unit

The total price for the cold drinks is stored in the `total_cold_drinks_price` variable.

After calculating the total prices for the medical items, grocery items, and cold drinks, the function updates the corresponding labels to display the calculated values.

Next, the function calculates the tax amount for the medical items, grocery items, and cold drinks. The tax rate for the medical items is 5%, for the grocery items is 5%, and for the cold drinks is 10%. The tax amounts are calculated by multiplying the total prices with the respective tax rates and rounding off to 2 decimal places.

The tax amounts for the medical items, grocery items, and cold drinks are stored in the `c_tax`, `g_tax`, and `c_d_tax` variables respectively.

The function then calculates the total bill amount by adding the total prices for the medical items, grocery items, and cold drinks, along with the tax amounts for each category.

Finally, the function updates the corresponding labels to display the total bill amount, medical tax, grocery tax, and cold drinks tax.

**Note**: This function is called when the "Total" button is clicked. It relies on the quantities of different items entered by the user and updates the calculated values accordingly. The calculated values are then displayed in the respective labels.
***
### FunctionDef welcome_bill(self)
**welcome_bill**: The function of welcome_bill is to display a welcome message and customer details in the billing software.

**parameters**:
- self: The instance of the class.

**Code Description**:
The `welcome_bill` function is responsible for displaying a welcome message and customer details in the billing software. It is called when the billing software is initialized or when the user wants to generate a new bill.

The function starts by clearing the text area where the bill details are displayed using the `delete` method of the `txtarea` Text widget. It then inserts the welcome message and customer details using the `insert` method of the `txtarea` Text widget.

The welcome message is displayed with the heading "Welcome Webcode Retail" and is inserted at the end of the text area using the `END` constant. The customer details, including the bill number, customer name, and phone number, are inserted below the welcome message.

After displaying the welcome message and customer details, the function inserts a separator line and a heading for the products section. This section will display the list of products, their quantities, and prices.

**Note**: This function is called by the `bill_area` function, which is responsible for generating the bill. It is also called when the billing software is initialized to display the welcome message and customer details.
***
### FunctionDef bill_area(self)
**bill_area**: The function of bill_area is to generate a bill for the customer based on the selected products and display it in the text area.

**parameters**:
- self: The instance of the class.

**Code Description**:
The `bill_area` function is responsible for generating the bill for the customer. It first checks if the customer details are provided and if any products are purchased. If the customer details are not provided or no products are purchased, it displays an error message using the `showerror` method of the `messagebox` module.

If the customer details are provided and at least one product is purchased, it calls the `welcome_bill` function to display the welcome message and customer details in the text area.

After displaying the welcome message and customer details, the function inserts the details of the purchased products in the text area. It checks the quantity of each product and if it is not zero, it inserts the product name, quantity, and price using the `insert` method of the `txtarea` Text widget.

The function then inserts the total bill amount and inserts a separator line. It also checks if there is any medical tax, grocery tax, or cold drinks tax applicable and inserts them in the text area if they are not zero.

Finally, the function calls the `save_bill` function to prompt the user to save the bill.

**Note**: This function is called by the `generateBill_btn` button in the `__init__` function of the `Bill_App` object. It is responsible for generating the bill based on the selected products and displaying it in the text area.

**Note**: Ensure that the necessary customer details are provided and at least one product is purchased before generating the bill.

**Note**: The `welcome_bill` function is called within this function to display the welcome message and customer details. The `save_bill` function is also called within this function to prompt the user to save the bill.

**Note**: The `welcome_bill` and `save_bill` functions are defined in the same file as this function.
***
### FunctionDef save_bill(self)
**save_bill**: The function of save_bill is to prompt the user to save a bill and write the bill data to a text file if the user chooses to save it.

**parameters**:
- None

**Code Description**:
The save_bill function first displays a message box asking the user if they want to save the bill. If the user confirms, the function retrieves the bill data from a text area, creates a new text file in the "bills" directory with the bill number as the filename, writes the bill data to the file, and displays a success message using a message box. If the user chooses not to save the bill, the function returns without performing any further actions.

The save_bill function is called within the bill_area function of the Bill_App object in the Billing_system project. In the bill_area function, after checking for necessary customer details and purchased products, the welcome_bill function is called to initiate the bill generation process. Once the bill details are displayed in the text area, the save_bill function is invoked to save the bill data to a text file.

**Note**:
- Ensure that the necessary customer details are provided before attempting to save the bill.
- Verify that at least one product has been purchased before saving the bill.

**Output Example**:
Saved Successfully:
Bill no: 001
--------------------------------
***
### FunctionDef find_bill(self)
**find_bill**: The function of find_bill is to search for a bill in the "bills/" directory based on the bill number entered by the user. If the bill is found, it is displayed in the text area of the GUI. If the bill is not found, an error message is displayed.

**parameters**:
- self: The instance of the class.

**Code Description**:
The find_bill function starts by initializing a variable called "present" with the value "no". This variable is used to keep track of whether the bill is found or not.

Next, it iterates over the files in the "bills/" directory using the os.listdir() function. For each file, it checks if the bill number (obtained by splitting the filename at the "." and taking the first part) matches the bill number entered by the user (stored in self.search_bill). If there is a match, it opens the file using the open() function and reads its contents line by line. The contents are then inserted into the text area of the GUI using the self.txtarea.insert() function. Finally, the file is closed.

If the bill is found, the "present" variable is set to "yes". If the bill is not found, an error message is displayed using the messagebox.showerror() function.

**Note**: 
- The "bills/" directory should exist and contain the bill files.
- The bill number entered by the user should match the filename of a bill file without the extension.
***
### FunctionDef clear_data(self)
**clear_data**: The function of clear_data is to reset all the variables and fields in the billing software to their initial values.

**parameters**:
- self: The instance of the class.

**Code Description**:
The `clear_data` function is responsible for resetting all the variables and fields in the billing software to their initial values. It is called when the user wants to clear the data and start fresh.

The function starts by displaying a message box asking the user if they really want to clear the data. If the user confirms by clicking "Yes", the function proceeds to reset all the variables and fields.

First, it sets the values of the medical items variables (`sanitizer`, `mask`, `hand_gloves`, `dettol`, `newsprin`, `thermal_gun`) to 0, indicating that none of these items have been selected.

Next, it sets the values of the grocery items variables (`rice`, `food_oil`, `wheat`, `daal`, `flour`, `maggi`) to 0, indicating that none of these items have been selected.

Then, it sets the values of the cold drinks items variables (`sprite`, `limka`, `mazza`, `coke`, `fanta`, `mountain_duo`) to 0, indicating that none of these items have been selected.

After resetting the item variables, it clears the values of the price variables (`medical_price`, `grocery_price`, `cold_drinks_price`) and the tax variables (`medical_tax`, `grocery_tax`, `cold_drinks_tax`).

Next, it clears the values of the customer details variables (`c_name`, `c_phone`) and the bill number variable (`bill_no`).

Then, it generates a new random bill number using the `random.randint` function and sets it as the value of the `bill_no` variable.

Finally, it clears the value of the search bill variable (`search_bill`) and calls the `welcome_bill` function to display the welcome message and customer details.

**Note**: This function is called when the user wants to clear the data and start fresh. It resets all the variables and fields in the billing software to their initial values.
***
### FunctionDef exit_app(self)
**exit_app**: The function of exit_app is to prompt the user with a message box asking if they really want to exit the application. If the user confirms the exit, the function will destroy the root window, effectively closing the application.

**parameters**:
- self: The reference to the current instance of the class.

**Code Description**:
The `exit_app` function is responsible for handling the exit functionality of the application. It starts by displaying a message box with the title "Exit" and the message "Do you really want to exit?". The `messagebox.askyesno` function is used to create a message box with Yes and No buttons. If the user clicks the Yes button (op > 0), the function proceeds to destroy the root window using the `self.root.destroy()` method.

This function is called when the user clicks the "Exit" button in the application's GUI. It provides a confirmation dialog to ensure that the user intends to exit the application. If the user confirms, the function terminates the application by destroying the root window.

**Note**:
- This function assumes that the `messagebox` module has been imported.
- The `self.root` attribute is expected to be a reference to the root window of the application.
- It is important to note that calling this function will immediately terminate the application without any further checks or saving of data.
***
