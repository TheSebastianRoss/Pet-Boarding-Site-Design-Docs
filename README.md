
## Features:
- Info pages
- Login page
- Application page for submitting info on the pets (animal type, age, breed,etc.), feeding schedules, special instructions, temperament(with humans, other pets),medications, time for drop-off and pickup, etc.
- Status page for pet owners to see information about their pets’ stay and updates from the people looking after the pets
- Update page for people looking after pets to send posts on the status page for the pet’s stay

## Data flow and UX
- ![Data Flow Context Diagram](/Diagrams/Data Flow Diagrams - Context Diagram.png)
 - Pet Owners can view company info from Public Web Pages
 - Pet Owners can fill reservation and pet info forms using the Pet Stay Reservation process
 - Pet Owners can access reservation and pet info using the Pet Stay Reservation process
 - Pet Owners can receive updates from the employee caretakers using the Pet Stay Reservation process
 - Employees can access reservation and pet info using the Pet Stay Reservation process 
 - Employees can fill in the updates form using the Pet Stay Reservation process

- ![Data Flow level 1 diagram](/Diagrams/Data Flow Diagram Level 1.png)
 - Data flows from Public Web Pages to the Pet Owner
 - Data flows from the Pet Owner to the Reservation process
 - Data flows from the Reservation process to the Reservation database
 - Data flows from the Reservation database to the Reservation process
 - Data flows from the Reservation process to the Employee
 - Data flows from the Reservation process to the Communication process
 - Data flows from the Pet Owner to the Communication process
 - Data flows from the Communication process to the Pet Owner
 - Data flows from the Reservation database to the Communication process
 - Data flows from the Communication process to the Employee
 - Data flows from the Employee to the Communication process

## Key entities and relationships
![Database Entity Relationship Diagram](/Diagrams/Database Diagram - Entity Relationship Diagram.png)
### Key entities
- Account
 - String: Username
 - String: Email
 - String: Phone
 - Login Credential\*
- Staff
- Pet
 - String: Species
 - String: Breed
 - Integer: Age
 - String: Sex
 - String: Temperament
 - String: Notes
- Reservation
 - Date: Start
 - Date: End
- Message
 - String: Content

\* Might depend on the type of login system we choose

### Relationships
- Directory:
  - Staff entries are associated with exactly 1 Directory entry.
  - Account entries are associated with either 0 or 1 Directory entries.
- Ownership:
  - Account entries are associated with 0 or more Ownership entries.
  - Pet entries are associated with exactly 1 Ownership entry.
- Stay:
  - Pet entries are associated with 0 or more Stay entries.
  - Reservation entries are associated with exactly 1 Stay entry.
- Update:
  - Reservation entries are associated with 0 or more Update entries.
  - Message entries are associated with exactly 1 Update entry.
- Author:
  - Account entries are associated with 0 or more Author entries.
  - Message entries are associated with exactly 1 Author entry.
