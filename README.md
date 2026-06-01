# 🏠 Hostel Listing Web Application

A modern full-stack web application for creating, managing, and browsing hostel listings with detailed information such as rent, facilities, location, weekly mess plans, and image galleries. This system is designed to make hostel discovery and listing simple, fast, and user-friendly for both owners and students.

---

## 🚀 Features

- Create and manage hostel listings
- Monthly rent and optional mess fee support
- Google Maps embed support for location
- Predefined + custom facilities system
- Weekly mess menu (7-day meal plan)
- Multiple image upload system
- Clean and modern responsive UI
- Mobile-friendly design
- EJS-based dynamic rendering

---

## 🛠️ Tech Stack

- Node.js
- Express.js
- EJS Templates
- MongoDB
- HTML, CSS, JavaScript
- Multer (file uploads)

---

## 📂 Project Structure

/project-root  
│  
├── /views  
│   ├── partials/  
│   ├── add_hostel.ejs  
│   ├── index.ejs  
│   └── hostel_details.ejs  
│  
├── /public  
│   ├── css/  
│   ├── js/  
│   └── uploads/  
│  
├── /routes  
│   └── hostelRoutes.js  
│  
├── /models  
│   └── Hostel.js  
│  
├── app.js  
├── package.json  
└── README.md  

---

## ⚙️ Installation & Setup

1. Clone the repository  
   git clone https://github.com/m0hammadusman/hostel-listing-app.git  

2. Move into the project directory  
   cd hostel-listing-app  

3. Install dependencies  
   npm install  

4. Create a .env file and add:  
   PORT=3000  
   MONGO_URI=your_mongodb_connection_string  

5. Start the server  
   npm start  

---

## 📌 Usage

- Open browser and go to http://localhost:3000  
- Click on “Add Hostel”  
- Fill in hostel details:
  - Name  
  - Category (Boys/Girls/Family)  
  - Area/City  
  - Rent and mess fee  
  - Facilities (including custom facilities)  
  - Weekly meal plan  
  - Upload images  
- Submit to publish listing  

---

## 🧩 Modules

### Hostel Management
Create, update, and manage hostel listings with full details.

### Facilities System
Supports both predefined and custom facilities added dynamically by users.

### Mess Menu System
Weekly structured meal plan for breakfast, lunch, and dinner for all 7 days.

### Image Upload System
Multiple image upload support for gallery display.

---

## 🎨 UI Highlights

- Modern glass-style UI design
- Fully responsive layout
- Smooth hover animations
- Clean and structured form design
- Card-based listing UI

---

## 📈 Future Improvements

- User authentication system (Admin/Owner/Student)
- Hostel search and filtering system
- Ratings and reviews
- Map-based hostel discovery
- Chat system between users
- Online booking feature

---

## 🤝 Contributing

1. Fork this repository  
2. Create a new branch  
3. Make your changes  
4. Submit a pull request  

---

## 📄 License

This project is licensed under the MIT License.

---

## 👨‍💻 Developer

Built with care to simplify hostel listing and discovery for students and property owners.
