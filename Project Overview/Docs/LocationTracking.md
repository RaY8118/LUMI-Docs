## **Frontend Flow**

1. **Page Load:**
    
    - When the user navigates to _map.jsx_, the app initializes the map component using **React Native Maps** or another map service.
    - The app fetches the current location from the backend using the function **fetchSavedLocation()** and updates the map with the user's position.
    - For patients, only their location is shown. For caregivers, locations of all linked patients are displayed.
2. **Map Interactions:**
    
    - Users can:
        - View the real-time position of tracked users.
        - Set the home location by tapping on the map (caregiver role only) using **`saveLocation`**.
        - Zoom and pan across the map for better visibility.
3. **Home Location Setting:**
    
    - The caregiver can mark a specific location as "home" by invoking the **`saveLocation`** function.
    - This triggers a local state update and sends the coordinates to the backend for storage in the `home_location` collection.
4. **Geofencing Alerts:**
    
    - Geofencing is implemented using **Expo Location**'s async function _watchPositionAsync_, which monitors changes in position at set intervals.
    - The patient's current location is periodically updated using the function **`saveCurrLocation`**.
    - The app calculates the distance between the current location and the saved home location using **`getDistanceFromLatLonInMeters`** to determine whether the user has breached the geofence.
5. **Utility Functions:**
    
    - **`getCurrentCoords`**: Fetches the device's current coordinates with high accuracy after requesting location permissions.
    - **`fetchSavedLocation`**: Retrieves the saved home location for a user from the backend.
    - **`saveLocation`**: Saves the current location as the home location in the backend.
    - **`saveCurrLocation`**: Periodically updates the backend with the user's live location for tracking purposes.

### **Backend Flow**

1. **Location Fetch:**
    
    - API Endpoint: `/safe-location?userId={userId}`
    - The frontend calls this endpoint to retrieve:
        - Patient(s)’ live location.
        - Home location (if set).
    - The location data is retrieved from the `location` collection in MongoDB.
2. **Live Updates:**
    
    - API Endpoint: `/curr-location`
    - Patients' devices periodically send their current location to the backend using this API.
    - The backend updates the `location` collection with the new coordinates.
3. **Home Location Storage:**
    
    - API Endpoint: `/safe-location`
    - Caregivers can send a request to this API with the selected home location.
    - The backend validates the data and updates the `location` collection.
---



# Flowchart
[[LocationFlow.png]]


