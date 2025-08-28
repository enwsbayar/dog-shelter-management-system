Dog Shelter Management System 🐕
This project is a web-based application developed to facilitate the management of dog shelters. It is built using the Flask framework and integrated with an SQLite database.

🚀 Features
General User Features
Animal List: View all animals in the shelter

Shelter Information: View shelter details

Search by ID: Search for animals and shelters by their ID

Staff Information: View shelter staff members

Shelter Owner Features
Secure Login: Password check with a shelter ID

Animal Management: Add new animals and list existing ones

Staff Management: Add new staff and list existing staff members

Examination Tracking: View examination records of treated animals

📁 Project Structure
dog-shelter-management/
├── Data/
│   └── data.xlsx              # Main data file
├── static/                    # CSS
├── templates/                 # HTML templates
├── database.py               # Database connection script
├── main.ipynb               # Main Flask application
├── randomDataGenerator.py    # Test data generator
├── veritabani.db            # SQLite database
└── README.md                # This file
🛠️ Installation
Requirements
Bash

pip install pandas
pip install pandasql
pip install flask
pip install openpyxl
pip install sqlite3
pip install webbrowser
Steps
Clone the repository

Bash

git clone https://github.com/enwsbayar/dog-shelter-management-system.git
cd dog-shelter-management-system
Install dependencies

Bash

pip install -r requirements.txt
Generate test data

Bash

python randomDataGenerator.py
Initialize the database

Bash

python database.py
Run the application

Bash

python main.ipynb
Open in your browser

http://127.0.0.1:5000
📊 Data Structure
Animal Table
HayvanId (AnimalId): Unique animal ID

Ad (Name): Animal's name

Tur (Type): Animal's species/breed

Cinsiyet (Gender): Male/Female

Yas (Age): Age information

SaglikDurumu (HealthStatus): Healthy/Sick/Under Treatment

GelisTarihi (ArrivalDate): Date of arrival at the shelter

BarinakId (ShelterId): ID of the shelter where the animal is located

Shelter Table
BarinakId (ShelterId): Unique shelter ID

Ad (Name): Shelter's name

Konum (Location): Shelter's location

Kapasite (Capacity): Maximum capacity

Sifre (Password): Shelter login password

Staff Table
PersonelId (StaffId): Unique staff ID

Ad (Name): Staff member's first name

Soyad (Surname): Staff member's last name

Gorev (Role): Role (Veterinarian, Caretaker, etc.)

CalismaTarihi (StartDate): Employment start date

BarinakId (ShelterId): ID of the shelter where they work

Veterinarian Table
VetId (VetId): Veterinarian ID (linked to StaffId)

Ad (Name): Veterinarian's first name

Soyad (Surname): Veterinarian's last name

Uzmanlik (Specialization): Area of specialization

Examination Table
MuayeneId (ExaminationId): Unique examination ID

HayvanId (AnimalId): ID of the animal examined

VeterinerId (VeterinarianId): ID of the veterinarian who performed the examination

Tarih (Date): Examination date

Teshis (Diagnosis): Diagnosis made

Tedavi (Treatment): Treatment applied

🔧 Usage
Shelter Owner Login
From the homepage, select "Shelter Owner Login"

Enter your Shelter ID (the same ID is used as the password)

After a successful login, you can access the management panel

Adding a New Animal
From the shelter owner panel, select "Add Animal"

Fill in the animal's details

If "Under Treatment" is selected as the health status, an automatic examination record is created

Adding a New Staff Member
From the shelter owner panel, select "Add Staff"

Fill in the staff member's details

If "Veterinarian" is selected as the role, an automatic veterinarian record is created

🎯 Test Data
You can automatically generate test data using the randomDataGenerator.py script:

28 shelters

500 animals

5 staff members per shelter (Veterinarian, Caretaker, Cleaner, Manager, Volunteer)

Examination records for treated animals

📝 Developer Notes
Technologies Used
Backend: Flask (Python)

Database: SQLite

Data Processing: Pandas, PandasQL

Excel Operations: OpenPyXL

Frontend: HTML, CSS

Important Files
main.ipynb: Main Flask application and route definitions

database.py: Transfers Excel data to SQLite

randomDataGenerator.py: Test data generation

Data/data.xlsx: Excel file containing all data sheets

Note: This system was developed for educational purposes. Security and performance tests are recommended before use in a real shelter environment.
