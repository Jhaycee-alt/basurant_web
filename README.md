🧹 BasuRANT: Waste Reporting & Management System
BasuRANT is a web-based waste reporting and management system that enables citizens to report waste issues, while allowing administrators and cleaners to manage, assign, and resolve reports efficiently.

🚀 Features
👤 Reporter (User)


Submit waste reports with:


Location (barangay, address, coordinates)


Description


Waste type & size


Images (photo, additional media)




Track report status


Receive notifications when reports are assigned or updated



🧑‍🔧 Cleaner


View assigned reports


Upload before and after cleanup images


Update report progress


Receive notifications when reports are assigned



🛠️ Admin


View all submitted reports


Assign reports to cleaners


Monitor report lifecycle (pending → in progress → completed)


Manage system-wide notifications



🔔 Notification System
The system uses a centralized server-driven notification architecture:


Notifications are created via admin server (service role)


Stored in Supabase database


Retrieved by users based on their role


Supports:


Real-time updates (optional)


Read/unread state persistence


UI filtering and clearing





🏗️ Tech Stack
Frontend


HTML, CSS, JavaScript


Modular JS architecture


Dynamic UI rendering


Backend (Admin Server)


Node.js (Express)


Supabase Admin Client (service role)


Database


Supabase (PostgreSQL)


Row Level Security (RLS)



🔐 Security Design


Service role key is never exposed to frontend


All notification inserts handled via backend API


RLS ensures:


Users can only read their own notifications


Users can only update their own read state





📁 Project Structure
project-root/│├── admin-server/        # Backend (Node.js)│   ├── server.js│   └── .env│├── public/              # Frontend files│   ├── report.html│   ├── cleaner.html│   ├── BasuRANT.html│   └── BasuRANT.js│├── README.md└── .gitignore

⚙️ Setup Instructions
1. Clone Repository
git clone https://github.com/your-username/basurant.gitcd basurant

2. Setup Admin Server
cd admin-servernpm install
Create .env:
SUPABASE_URL=your_urlSUPABASE_SERVICE_ROLE_KEY=your_service_role_keyADMIN_API_KEY=your_secret_key
Run server:
node server.js

3. Run Frontend
Open:
report.htmlcleaner.htmlBasuRANT.html
Or use a local server:
npx serve

🧪 Testing


Submit a report as reporter


Assign report as admin


Verify:


Cleaner receives notification


Reporter receives notification


Read state persists


UI updates correctly





⚠️ Known Limitations


Real-time updates may require Supabase subscriptions setup


UI duplication may occur if multiple render pipelines are active (resolved in latest version)


Requires proper RLS configuration



📌 Future Improvements


Full real-time notification system


Mobile responsiveness


Analytics dashboard


Role-based UI isolation improvements


Codebase modularization



📜 License
This project is licensed under the MIT License.

👨‍💻 Author
Developed by Johndrell Cesar Dilan

💬 Final Note
This project demonstrates:


Full-stack integration (frontend + backend + database)


Secure handling of privileged operations


Real-world system design with role-based workflows
