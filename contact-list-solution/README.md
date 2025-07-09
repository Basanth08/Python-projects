# Contact List Manager

I built a comprehensive contact management system with CRUD operations, input validation, and persistent JSON storage. It's designed to help you keep track of all your important contacts in one place.

## 📞 What I Built

- **Add Contacts**: I created a system that lets you create new contacts with full details
- **Search Contacts**: I made it so you can find contacts by first or last name
- **List All Contacts**: I built a feature to view all contacts in alphabetical order
- **Delete Contacts**: I added the ability to remove contacts with confirmation
- **Input Validation**: I included phone number and email validation
- **Persistent Storage**: I used JSON file-based data persistence
- **Duplicate Prevention**: I made sure you can't add contacts with the same name

## 📁 How I Structured the Project

```
contact-list-solution/
├── main.py          # I put the main application with menu system here
├── storage.py       # I handle JSON file I/O operations here
└── util.py          # I created validation utilities here
```

## 🚀 Getting Started

### What You'll Need
- Python 3.6+ (I used features that require this version)
- No external dependencies (I kept it simple!)

### How to Run My Application

```bash
cd contact-list-solution
python main.py
```

## 🎯 How I Made It Work

### Contact Information I Store
Each contact I save includes:
- **First Name** (I made this required)
- **Last Name** (I made this required)
- **Mobile Phone** (I made this optional, but validated)
- **Home Phone** (I made this optional, but validated)
- **Email Address** (I made this optional, but validated)
- **Address** (I made this optional)

### Validation Rules I Created

#### Phone Numbers
- I made it so they must be exactly 10 digits
- I added support for hyphens (I automatically remove them)
- I only allow numeric characters

#### Email Addresses
- I made sure they contain exactly one "@" symbol
- I require text before and after "@"
- I made the domain contain at least one "."
- I prevent empty sections in the domain

## 🎮 Available Commands I Built

### `add` - Add a New Contact
```
First Name: john
Last Name: doe
Mobile Phone Number: 555-123-4567
Home Phone Number: 555-987-6543
Email Address: john.doe@example.com
Address: 123 Main St, City, State
Contact Added!
```

### `search` - Find Contacts
```
First Name: john
Last Name: 
Found 1 matching contacts.
1. John Doe
    Mobile: 555-123-4567
    Home: 555-987-6543
    Email: john.doe@example.com
    Address: 123 Main St, City, State
```

### `list` - View All Contacts
```
1. Alice Johnson
    Mobile: 555-111-2222
    Email: alice@example.com

2. Bob Smith
    Home: 555-333-4444
    Address: 456 Oak Ave

3. John Doe
    Mobile: 555-123-4567
    Home: 555-987-6543
    Email: john.doe@example.com
    Address: 123 Main St, City, State
```

### `delete` - Remove a Contact
```
First Name: john
Last Name: doe
Are you sure you would like to delete this contact (y/n)? y
Contact deleted!
```

### `q` - Quit and Save
```
Type a command: q
Contacts were saved successfully.
```

## 🔧 Technical Details I Implemented

### Key Functions I Built

#### `main.py`
- **`add_contact()`**: I made it handle contact creation with validation
- **`search_for_contact()`**: I built partial name matching
- **`delete_contact()`**: I added safe deletion with confirmation
- **`list_contacts()`**: I created sorted display of all contacts
- **`get_contact_string()`**: I made it format contacts for display

#### `storage.py`
- **`read_contacts()`**: I made it load contacts from JSON file
- **`write_contacts()`**: I built it to save contacts to JSON file
- **Error Handling**: I made it create empty list if file doesn't exist

#### `util.py`
- **`verify_phone_number()`**: I created phone number format validation
- **`verify_email_address()`**: I built email format validation
- **`get_contact_by_name()`**: I made it find exact name matches

### Data Structure I Used

```json
{
  "contacts": [
    {
      "first_name": "john",
      "last_name": "doe",
      "mobile": "555-123-4567",
      "home": "555-987-6543",
      "email": "john.doe@example.com",
      "address": "123 Main St, City, State"
    }
  ]
}
```

## 🛡️ Error Handling I Built

### Input Validation
- **Required Fields**: I made first and last name mandatory
- **Phone Validation**: I reject invalid phone numbers
- **Email Validation**: I reject malformed email addresses
- **Duplicate Names**: I prevent adding contacts with same name

### File Operations
- **Missing File**: I made it create new file if contacts.json doesn't exist
- **Corrupted File**: I added graceful handling of JSON parsing errors
- **Write Protection**: I handle file permission issues

## 📊 Search Functionality I Created

### Partial Matching
- **First Name**: I made it match any part of first name
- **Last Name**: I made it match any part of last name
- **Case Insensitive**: I made search not case-sensitive
- **Empty Fields**: I made empty search fields match all contacts

### Search Examples
```
First Name: jo
Last Name: 
Found 2 matching contacts.
1. John Doe
2. Joseph Smith
```

## 🔄 Data Flow I Designed

```
Start App → Load Contacts → Display Menu → Get Command → 
Process Command → Update Data → Save to File → Continue/Quit
```

## 📈 Performance Features I Optimized

### Efficient Operations
- **O(n) Search**: I made linear search through contacts
- **O(n log n) Sort**: I used efficient sorting for display
- **Minimal I/O**: I only save when you quit
- **Memory Efficient**: I load entire file once

### User Experience
- **Case Insensitive**: I made commands work regardless of case
- **Flexible Input**: I handle extra whitespace
- **Clear Feedback**: I give informative error messages
- **Confirmation Prompts**: I added safe deletion with confirmation

## 🎯 What I Learned Building This

This project taught me:
- File I/O operations with JSON
- Input validation and sanitization
- CRUD operations (Create, Read, Update, Delete)
- String manipulation and formatting
- Error handling and user feedback
- Data persistence
- Search algorithms
- User interface design
- Data structure management

## 🔧 Customization I Made Possible

### Adding New Fields
To add new contact fields:
1. I made it so you can update the contact dictionary in `add_contact()`
2. I designed it so you can add validation logic in `util.py`
3. I made it easy to update display formatting in `get_contact_string()`

### Changing Validation Rules
- I made it so you can modify `verify_phone_number()` for different phone formats
- I designed it so you can update `verify_email_address()` for stricter email validation
- I made it easy to add new validation functions as needed

### Storage Format
- I made it so you can change from JSON to CSV, SQLite, or other formats
- I designed it so you can modify `storage.py` functions accordingly
- I made it easy to update data structure handling in main application 