
ContactBook = []

def display():
    print("1. Add Contact")
    print("2. View List")
    print("3. Exit")
   

def add_contact():
    contact = {}  # Create a dictionary for each contact
    contact['Name'] = input("Enter the name of the contact: ")
    
    # Ensure valid phone number with 10 digits
    while True:
        phone = input("Enter the phone number (10 digits): ")
        if phone.isdigit() and len(phone) == 10:
            contact['Phone Number'] = phone
            break
        else:
            print("Invalid phone number. Please enter a 10-digit number.")
    
    contact['Email'] = input("Enter the email: ")
    contact['Address'] = input("Enter the address: ")
    
    ContactBook.append(contact)  # Add the dictionary to ContactBook

def view_contacts():
    if ContactBook:
        for i, contact in enumerate(ContactBook, 1):
            print(f"Contact {i}:")
            for key, value in contact.items():
                print(f"{key}: {value}")
            print("------")
    else:
        print("Contact Book is empty.")

def main():
    while True:
        display()
        try:
            choice = int(input("Enter a choice: "))
        except ValueError:
            print("Invalid choice. Please enter a number.")
            continue
        
        if choice == 1:
            add_contact()  # Add a new contact
        elif choice == 2:
            view_contacts()  # View the list of contacts
        elif choice == 3:
            print("Exiting...")
            break
        else:
            print("Invalid option. Please try again.")

if __name__ == "__main__":
    main()


        
