class Contact:
    def __init__(self, name, phone, email):
        self.name = name
        self.phone = phone
        self.email = email

class ContactList:
    def __init__(self):
        self.contacts = []
    
    def add_contact(self, contact):
        self.contacts.append(contact)
    
    def view_contacts(self):
        for idx, contact in enumerate(self.contacts, start=1):
            print(f"Contact {idx}:")
            print(f"Name: {contact.name}")
            print(f"Phone: {contact.phone}")
            print(f"Email: {contact.email}")
            print("-" * 20)
    
    def search_contact(self, search_name):
        found_contacts = []
        for contact in self.contacts:
            if search_name.lower() in contact.name.lower():
                found_contacts.append(contact)
        
        if found_contacts:
            print(f"Found {len(found_contacts)} matching contacts:")
            for idx, contact in enumerate(found_contacts, start=1):
                print(f"Match {idx}:")
                print(f"Name: {contact.name}")
                print(f"Phone: {contact.phone}")
                print(f"Email: {contact.email}")
                print("-" * 20)
        else:
            print("No matching contacts found.")

def main():
    contact_list = ContactList()
    
    while True:
        print("Contact List Menu:")
        print("1. Add Contact")
        print("2. View Contacts")
        print("3. Search Contacts")
        print("4. Exit")
        
        choice = input("Enter choice (1/2/3/4): ")
        
        if choice == '1':
            name = input("Enter name: ")
            phone = input("Enter phone number: ")
            email = input("Enter email: ")
            new_contact = Contact(name, phone, email)
            contact_list.add_contact(new_contact)
            print("Contact added.")
        elif choice == '2':
            contact_list.view_contacts()
        elif choice == '3':
            search_name = input("Enter name to search: ")
            contact_list.search_contact(search_name)
        elif choice == '4':
            print("Exiting the program.")
            break
        else:
            print("Invalid choice. Please enter a valid option.")

if __name__ == "__main__":
    main()
