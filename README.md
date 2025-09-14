# Python-program-task-2
# Contact Book Program in Python

contacts = {}  # Dictionary to store contacts

def add_contact():
    name = input("Enter Name: ")
    phone = input("Enter Phone Number: ")
    email = input("Enter Email: ")
    address = input("Enter Address: ")
    contacts[name] = {"Phone": phone, "Email": email, "Address": address}
    print("✅ Contact added successfully!\n")

def view_contacts():
    if not contacts:
        print("No contacts found!\n")
    else:
        print("\n--- Contact List ---")
        for name, details in contacts.items():
            print(f"Name: {name}, Phone: {details['Phone']}")
        print()

def search_contact():
    name = input("Enter name to search: ")
    if name in contacts:
        print("\n--- Contact Found ---")
        print(f"Name: {name}")
        print(f"Phone: {contacts[name]['Phone']}")
        print(f"Email: {contacts[name]['Email']}")
        print(f"Address: {contacts[name]['Address']}\n")
    else:
        print("Contact not found!\n")

def update_contact():
    name = input("Enter the name of contact to update: ")
    if name in contacts:
        print("Enter new details (leave blank to keep old):")
        phone = input(f"New Phone ({contacts[name]['Phone']}): ") or contacts[name]['Phone']
        email = input(f"New Email ({contacts[name]['Email']}): ") or contacts[name]['Email']
        address =  input(f"New Address ({contacts[name]['Address']}): ") or contacts[name]['Address']
        contacts[name] = {"Phone": phone, "Email": email, "Address": address}
        print("✅ Contact updated successfully!\n")
    else:
        print("Contact not found!\n")

def delete_contact():
    name = input("Enter the name of contact to delete: ")
    if name in contacts:
        del contacts[name]
        print("🗑 Contact deleted successfully!\n")
    else:
        print("Contact not found!\n")

def menu():
    while True:
        print("===== Contact Book =====")
        print("1. Add Contact")
        print("2. View Contact List")
        print("3. Search Contact")
        print("4. Update Contact")
        print("5. Delete Contact")
        print("6. Exit")
        choice = input("Enter your choice (1-6): ")

        if choice == "1":
            add_contact()
             elif choice == "2":
            view_contacts()
        elif choice == "3":
            search_contact()
        elif choice == "4":
            update_contact()
        elif choice == "5":
            delete_contact()
        elif choice == "6":
            print("Exiting Contact Book. Goodbye! 👋")
            break
        else:
            print("Invalid choice! Please try again.\n")

# Run the program
menu()
