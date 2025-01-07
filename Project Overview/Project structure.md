## Frontend
/lumi
├── /app                      # Expo Router navigation folder
│   ├── (auth)                # Authentication-related screens [[UserLogic]]
│   │   ├── sign-in.jsx  
│   │   ├── sign-up.jsx
│   │   ├── forgot-password.jsx
│   │   └── layout.jsx
│   ├── (tabs)                # Tab-based navigation screens
│   │   ├── layout.jsx
│   │   ├── reminders.jsx       # Reminders Page [[Reminders]]
│   │   ├── map.jsx        # Location Tracking  [[LocationTracking]]
│   │   ├── chat.jsx
│   │   ├── camera.jsx   # Face and Object detection [[FaceObjectDetection]]
│   │   ├── profile.jsx    # Profile Page   [[Profile]]
│   ├── App.js   
│   ├── layout.js   
│   └── index.jsx             # Entry point, usually default home
├── /assets                   # Static assets like images, fonts, etc.
│   ├── /images
│   ├── /fonts
│   └── ...
├── /components               # Reusable components
│   ├── CustomButton.jsx
│   ├── CustomInput.jsx
│   ├── AddModelComponent.jsx
│   ├── EditModalComponent.jsx
│   └── ...
├── /constants                 # Constant API files
│   ├── Colors.ts
│   ├── Icons.js
│   ├── Images.js
│   └── ...
├── /contexts                 # Context API files (e.g., userContext)
│   ├── userContext.jsx    [[UserContext]]
│   └── ...
├── /hooks                    # Custom hooks
│   └── ...
├── /services                 # API and backend service integrations
│   ├── authService.js
│   ├── cameraService.js
│   ├── locationService.js
│   ├── remindersService.js
│   └── ...
├── /utils                    # Utility/helper functions
│   └── ...
│   ├     # For nativewindcss
│   └── ...
├── app.config.js             # Expo app configuration
├── package.json              # Dependencies and scripts
├── babel.config.js           # Babel configuration
├── tailwind.config.js
└── README.md                 # Project documentation





## Backend
/linux_backend
├── /app                  
│   ├── init.py          
│   ├── auth.py          
│   ├── img_processing.py
│   ├── location.py          
│   ├── relations.py          
│   ├── reminder.py 
│   ├── routes.py        
├── /config                  
│   ├── /config.py
├── /images           
│   ├── ...
├── /model            
│   ├── yolov10b.pt
├── /resources              
│   ├──family_famID_encodefile.p
│   └── ...
├── requirements.txt 
├── run.py
└── README.md            