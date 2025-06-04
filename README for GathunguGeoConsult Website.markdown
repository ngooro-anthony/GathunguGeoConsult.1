# GathunguGeoConsult Website

## Overview
This project is a web application for GathunguGeoConsult, a GIS and Geomatics service provider. It includes a customer-facing site for browsing services, requesting services, and viewing FAQs, plus a restricted admin panel for managing services and customer requests.

## Features
### Customer-Facing
- **Service Listings**: Displays services like Topographic Survey, Land Parcel Mapping, and GIS Data Analysis with price ranges (e.g., Ksh 5,000 - 10,000).
- **Search Functionality**: Search bar to filter services by name or description.
- **Service Request Form**: Users select a service and provide a mobile number; no login required.
- **Basic Pricing Guide**: Shows price ranges for transparency.
- **FAQ Section**: Answers common questions about services.
- **Confirmation Message**: Displays on successful request submission.
- **Photos/Visuals**: Placeholder images of surveyors using equipment.
- **Planned Additions**: Testimonials and About page.

### Admin Panel
- **Access Restriction**: Hidden from public view; requires a secret URL parameter (e.g., `/admin?key=gathungu-secret-2025`) to access login.
- **Admin Login**: Secure authentication for admin access.
- **Admin Capabilities**: Add, update, and delete services; view and delete customer requests.

### Design & Branding
- **Professional Look**: Clean, consistent design.
- **Color Palette**:
  - Green (#4CAF50) for headers and accents.
  - Red (#D32F2F) for service titles and delete buttons.
  - Yellow (#FBC02D) for price ranges.
  - Blue (#1976D2) for navigation and buttons.
- **Consistent Branding**: Unified style across pages.

### Security & Hosting
- **Security Layers**:
  - Basic XSS protection via input sanitization in frontend.
  - Admin route protected by a secret key and login.
- **Hosting Support**: Deployable on any Flask-compatible host (e.g., Heroku, AWS, etc.); hosting setup assistance provided post-development.

### Technologies
- **Framework**: Python with Flask.
- **Database**: SQLite via SQLAlchemy for services, requests, and admin credentials.
- **Frontend**: HTML, CSS, and JavaScript for dynamic interaction.

## Setup Instructions
1. **Prerequisites**:
   - Python 3.8 or higher
   - pip (Python package manager)
2. **Installation**:
   - Clone this repository: `git clone <repository-url>`
   - Navigate to the project directory: `cd gathungugeoconsult`
   - Install dependencies: `pip install flask flask-sqlalchemy werkzeug`
3. **File Structure**:
   - `app.py`: Flask backend with routes and database logic.
   - `index.html`: Home page.
   - `services.html`: Services listing page.
   - `request.html`: Service request form page.
   - `faq.html`: FAQ page.
   - `admin.html`: Restricted admin panel.
   - Place HTML files in a `templates` folder.
4. **Database Setup**:
   - The app uses SQLite; a `gathungugeoconsult.db` file is created automatically on first run.
5. **Running the App**:
   - Run `python app.py` to start the Flask server in debug mode.
   - Access the site at `http://localhost:5000`.
6. **Admin Access**:
   - Navigate to `http://localhost:5000/admin?key=gathungu-secret-2025` for the admin login.
   - Default credentials: Username: `admin`, Password: `securePass123`.
   - Replace with secure credentials in production.

## Usage
- **Customer Pages**:
  - Home: `/` - Welcome message and navigation.
  - Services: `/services` - View and search services.
  - Request: `/request` - Submit a service request.
  - FAQ: `/faq` - Read common questions and answers.
- **Admin Panel**:
  - Access via `/admin?key=gathungu-secret-2025`.
  - Log in to manage services and view/delete requests.
  - Secret key restricts visibility; share only with the owner.

## Planned Future Enhancements
- Fully styled, responsive UI.
- Client-ready, polished structure.
- Contact confirmation page/message.
- Proper error handling and validation.
- Expanded admin dashboard.
- Testimonials and About section.
- Potential email/SMS notifications for admin or customer.

## Notes
- The admin panel is hidden by requiring a secret key in the URL. Update `ADMIN_ACCESS_KEY` in `app.py` for production.
- Replace placeholder images (`https://via.placeholder.com`) with real surveyor photos.
- Secure the admin password and database for production use.
- Test thoroughly before deployment.

## Deployment
- Choose a hosting provider (e.g., Heroku, AWS, Render).
- Configure environment variables for the database URI and admin key.
- Ensure HTTPS for security.
- Assistance for hosting setup will be provided upon completion.