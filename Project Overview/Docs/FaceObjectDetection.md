#### **1. Taking a Picture:**

- **Function:** `takePicture`
- **Purpose:** Captures a photo using the camera reference provided.
- **Details:**
    - Checks if the `cameraRef` is valid.
    - Calls `takePictureAsync()` to take a picture.
    - Returns the URI of the captured image.

---

#### **2. Resizing the Image:**

- **Function:** `resizeImage`
- **Purpose:** Resizes the captured image to the required dimensions for efficient processing.
- **Details:**
    - Uses `expo-image-manipulator` to resize the image to **816 x 1088** pixels.
    - Compresses the image to 80% quality and saves it in JPEG format.
    - Returns the URI of the resized image.

---

#### **3. Uploading the Image:**

- **Function:** `uploadImage`
- **Purpose:** Sends the resized image to the backend for processing.
- **Details:**
    - Constructs a `FormData` object containing the image.
    - Sends the image to the specified `endpoint` using an HTTP POST request via `axios`.
    - Differentiates between **face recognition** and **object detection** using the `isFaceRecognition` flag:
        - For **Face Recognition**:
            - Displays the detected names or a message saying "No faces found."
        - For **Object Detection**:
            - Displays the identified objects or a message saying "No objects found."
    - Handles errors and displays appropriate alerts.

---

#### **4. Handling Face Recognition:**

- **Function:** `handleFaceRecognition`
- **Purpose:** Integrates all steps for face recognition.
- **Steps:**
    - Calls **`takePicture`** to capture a photo.
    - Resizes the photo using **`resizeImage`**.
    - Sends the resized photo to the backend using **`uploadImage`** with the endpoint `${apiUrl}/detect_faces/${user.familyId}`.
    - Processes the backend response to display recognized faces or errors.

---

#### **5. Handling Object Detection:**

- **Function:** `handleObjectDetection`
- **Purpose:** Integrates all steps for object detection.
- **Steps:**
    - Calls **`takePicture`** to capture a photo.
    - Resizes the photo using **`resizeImage`**.
    - Sends the resized photo to the backend using **`uploadImage`** with the endpoint `${apiUrl}/obj-detection`.
    - Processes the backend response to display identified objects or errors.

---

