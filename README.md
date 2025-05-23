# Student Enrollment Form using JSONPowerDB

This project is a **Student Enrollment Form** that stores student records in a JSONPowerDB database. It supports adding new student records, updating existing records, and resetting the form. The data is stored in the `STUDENT-TABLE` relation of the `SCHOOL-DB` database on JSONPowerDB.

---

## Features

- Input fields:  
  - Roll-No (Primary Key)  
  - Full-Name  
  - Class  
  - Birth-Date  
  - Address  
  - Enrollment-Date

- Controls:  
  - **Save**: Insert a new student record if the Roll-No does not exist.  
  - **Update**: Update an existing student record if the Roll-No exists.  
  - **Reset**: Clear the form and reset state.

- Form behavior:  
  - Initially, only the Roll-No field is enabled.  
  - After entering Roll-No, the form checks if the Roll-No exists in the database.  
  - If not found, enables Save and Reset, and allows input of other fields.  
  - If found, loads existing data, enables Update and Reset, disables Roll-No editing.  
  - Validates all fields before saving or updating.

- Uses JSONPowerDB APIs (`GET_BY_KEY`, `PUT`, `UPDATE`) for database operations.

---

## Technologies Used

- **Frontend:** HTML, CSS, JavaScript (Vanilla)  
- **Backend:** JSONPowerDB (No backend code required, uses JSONPowerDB cloud APIs)

---
## Release History

{
  "releaseHistory": [
{
"version": "1.0.0",
"date": "2025-05-23",
"description": "Initial release with Save, Update, Reset functionality for Student Enrollment Form using JSONPowerDB APIs."
}
]
}




---
### Example PUT Request String for Inserting a Student Record
owe
function createPUTRequest(connToken, jsonObj, dbName, relName) {
    var putRequest = "{\n"
        + "\"token\" : \"" + connToken + "\",\n"
        + "\"dbName\": \"" + dbName + "\",\n"
        + "\"cmd\" : \"PUT\",\n"
        + "\"rel\" : \"" + relName + "\",\n"
        + "\"jsonStr\": " + JSON.stringify(jsonObj) + "\n"
        + "}";
    return putRequest;
}


## How to Use

1. **Set Up JSONPowerDB:**
   - Create a database named `SCHOOL-DB`.
   - Create a relation named `STUDENT-TABLE` with the following template:

   ```json
   {
     "Roll-No": "string",
     "Full-Name": "string",
     "Class": "string",
     "Birth-Date": "string",
     "Address": "string",
     "Enrollment-Date": "string"
   }
