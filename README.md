Anti-Corruption Information System (ACIS)

The Anti-Corruption Information System (ACIS) is a full-stack, government-ready web application designed to empower citizens to report corruption safely and give authorized officials the tools to investigate, track, and resolve every case with documented accountability.

Key Features

Citizen Portal

Secure Registration & Login: Password-protected accounts backed by bcrypt hashing and JSON Web Tokens (JWT).

Anonymous or Named Reporting: Citizens can choose to hide their identity from administrative views while still tracking their case.

Interactive Location Pinning: Built with Leaflet.js and OpenStreetMap so reporters can drop a pin on the exact incident location.

Evidence Uploads: Supports attaching photos, documents, or other files directly to a report via Multer.

Case Tracking: Unique tracking codes (ACIS-XXXXXX) allow citizens to monitor investigation progress in real time.

Government Admin Dashboard

Role-Based Access Control (RBAC): Strictly restricted to authenticated administrator accounts.

Case Management: View all incoming reports, inspect uploaded evidence, update case statuses (Pending, Review, Resolved, Rejected), and add official investigation notes.

Public News Publishing: Officials can publish investigative outcomes and summaries directly to the Public News Feed for citizen transparency.

PDF Summary Export: One-click generation of downloadable PDF audit reports using jsPDF.

Technology Stack

Frontend: HTML5, CSS3, Vanilla JavaScript (ES6+), Leaflet.js, jsPDF

Backend: Node.js, Express.js

Database: SQLite (database.sqlite)

Security & Storage: Bcrypt, JSON Web Tokens (JWT), Multer (local file uploads)

Hosting: Render (Backend) & GitHub Pages (Frontend)

Local Setup & Installation

Clone the repository:

git clone <your-repository-url>
cd <your-project-folder>


Install dependencies:

npm install


Start the backend server:

node server.js


The server will start on http://localhost:3000 and automatically initialize the SQLite database (database.sqlite) and uploads/ directory.

Launch the frontend:
Open index.html directly in your web browser (or via a local development server).

Default Admin Credentials

When the server runs for the first time, it automatically creates a default government administrator account:

Email: admin@acis.gov

Password: AdminSecure2026!

Security Note: Be sure to update or remove these default credentials and set a strong JWT_SECRET environment variable before deploying to a live production environment.

Cloud Deployment

Backend (Render):

Build Command: npm install --build-from-source

Start Command: node server.js

Environment Variable: NODE_VERSION set to 20.12.2 (recommended for native SQLite compatibility).

Frontend (GitHub Pages):

Update all http://localhost:3000 API URLs in index.html to your live Render backend URL, then enable GitHub Pages on your frontend repository.
