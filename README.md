
# Dog Shelter Management System 🐕

This project is a web-based application designed to simplify the management of dog shelters. It is developed using the Flask framework and integrated with an SQLite database.

## 🚀 Features

### General User Features
- **Animal List**: View all animals in the shelter
- **Shelter Information**: View shelter details
- **Search by ID**: Search by animal or shelter ID
- **Staff Information**: View shelter staff

### Shelter Owner Features
- **Secure Login**: Password verification with shelter ID
- **Animal Management**: Add new animals and list existing ones
- **Staff Management**: Add new staff and list existing staff
- **Check-up Tracking**: View check-up records of treated animals

## 📁 Project Structure

```
dog-shelter-management/
├── Data/
│   └── data.xlsx              # Main data file
├── static/                    # CSS files
├── templates/                 # HTML templates
├── database.py               # Database connection script
├── main.ipynb               # Main Flask application
├── randomDataGenerator.py    # Test data generator
├── veritabani.db            # SQLite database
└── README.md                # This file
```

## 🛠️ Installation

### Requirements
```
pip install pandas
pip install pandasql
pip install flask
pip install openpyxl
pip install sqlite3
pip install webbrowser
```

### Steps
1. **Clone the repository**
```
git clone https://github.com/enwsbayar/dog-shelter-management-system.git
cd dog-shelter-management-system
```
2. **Install dependencies**
```
pip install -r requirements.txt
```
3. **Generate test data**
```
python randomDataGenerator.py
```
4. **Initialize the database**
```
python database.py
```
5. **Run the application**
```
python main.ipynb
```
6. **Open in your browser**
```
http://127.0.0.1:5000
```

## 📊 Data Structure

### Animal Table
- **AnimalId**: Unique animal ID
- **Name**: Animal name
- **Species**: Animal species/breed
- **Gender**: Male/Female
- **Age**: Age information
- **HealthStatus**: Healthy/Sick/Under Treatment
- **ArrivalDate**: Date of arrival at the shelter
- **ShelterId**: Shelter ID where the animal is located

### Shelter Table
- **ShelterId**: Unique shelter ID
- **Name**: Shelter name
- **Location**: Shelter location
- **Capacity**: Maximum capacity
- **Password**: Shelter login password

### Staff Table
- **StaffId**: Unique staff ID
- **FirstName**: Staff first name
- **LastName**: Staff last name
- **Role**: Role (Veterinarian, Caretaker, etc.)
- **StartDate**: Employment start date
- **ShelterId**: Shelter ID where staff works

### Veterinarian Table
- **VetId**: Veterinarian ID (linked to StaffId)
- **FirstName**: Veterinarian first name
- **LastName**: Veterinarian last name
- **Specialty**: Field of expertise

### Checkup Table
- **CheckupId**: Unique checkup ID
- **AnimalId**: Checked animal ID
- **VeterinarianId**: Performing veterinarian ID
- **Date**: Checkup date
- **Diagnosis**: Diagnosis
- **Treatment**: Applied treatment

## 🔧 Usage

### Shelter Owner Login
1. Select "Shelter Owner Login" on the main page
2. Enter your shelter ID (used as password as well)
3. Upon successful login, access the management panel

### Add New Animal
1. In the shelter owner panel, select "Add Animal"
2. Fill in animal information
3. If Health Status is "Under Treatment", a checkup record is automatically created

### Add New Staff
1. In the shelter owner panel, select "Add Staff"
2. Fill in staff information
3. If Role is "Veterinarian", a veterinarian record is automatically created

## 🎯 Test Data

You can generate automatic test data using `randomDataGenerator.py`:
- 28 shelters
- 500 animals
- 5 staff per shelter (Veterinarian, Caretaker, Cleaner, Manager, Volunteer)
- Checkup records for treated animals

## 📝 Developer Notes

### Technologies Used
- **Backend**: Flask (Python)
- **Database**: SQLite
- **Data Processing**: Pandas, PandasQL
- **Excel Handling**: OpenPyXL
- **Frontend**: HTML, CSS

### Important Files
- `main.ipynb`: Main Flask application and route definitions
- `database.py`: Transfers Excel data to SQLite
- `randomDataGenerator.py`: Test data generation
- `Data/data.xlsx`: Excel file containing all data sheets

**Note**: This system is developed for educational purposes. Prior to real-world usage, security and performance testing is recommended.
