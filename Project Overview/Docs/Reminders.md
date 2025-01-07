### **Reminders Workflow**

#### **1. Create Reminder**

- The user fills out the reminder form on the _main.jsx_ page, including the title, description, urgency, and importance.
- On submission, the **postReminders()** function triggers an API POST request to `/reminder` in the Flask backend.
- The backend validates the input and stores the reminder in the MongoDB `reminders` collection, associating it with the user's `userID`.
- The new reminder is added to the reminders list displayed on the frontend.

#### **2. Read/Fetch Reminders**

- Upon loading the reminders page, the **fetchReminders()** function sends a GET request to `/reminders?userId={userId}`.
- The backend retrieves all reminders linked to the logged-in user's `userID` from MongoDB.
- The fetched reminders are displayed in a list view on _main.jsx_, allowing users to view details like urgency and importance.

#### **3. Update Reminder**

- The user selects a reminder and edits the details using a modal component (_EditModalComponent.jsx_).
- The **updateReminder()** function sends a PUT request to `/reminder` with the updated reminder data.
- The backend updates the corresponding entry in the MongoDB `reminders` collection and sends a success response.
- The frontend updates the reminders list with the edited reminder in real time.

#### **4. Delete Reminder**

- The user clicks the delete button for a specific reminder in the reminders list.
- The **deleteReminder()** function triggers a DELETE request to `/reminder/{remId}` with the reminder's unique ID.
- The backend removes the reminder from the MongoDB `reminders` collection.
- The frontend refreshes the reminders list, removing the deleted item.
### **Flowchart**

[[RemindersLogic.png]]