# Professional Portfolio with Flask Application

This project is a professional portfolio website built using Flask, a lightweight web framework for Python. The application is designed to showcase projects, skills, and experience in a clean and responsive manner. README provides instructions on how to set up and run the application locally, as well as how to deploy it using Gunicorn and Nginx for production.

## Prerequisites

- **Python 3.8+** installed on your system
- **pip** (Python package manager)
- **Git** (for version control)
- **Nginx** installed and configured (optional, for production deployment)
- **Linux/Mac/Windows** with terminal access

### 1. Clone or Download the Project

```bash
cd ~ && git clone https://github.com/jmuraris/Portfolio.git
# or just extract the project folder
cd Portfolio
```
### 2. Run the script to set up the environment and run the application

```bash
./run.sh
```

The above script will do the following:

### 3. Create a Virtual Environment

Virtual environments are isolated Python environments for your project, preventing dependency conflicts.

```bash
# Navigate to project directory
cd Portfolio

# Create virtual environment
python3 -m venv .venv

# Activate virtual environment
# On Linux/Mac:
source .venv/bin/activate
# On Windows:
.venv\Scripts\activate
```

You should see `(venv)` prefix in your terminal when activated.

### 4. Install Dependencies

```bash 
pip install -r requirements.txt
```
This will install all the required Python packages for the Flask application.

### 5. Run the Flask Application with Gunicorn

```bash
gunicorn -w 2 -b 0.0.0.0:8000 app:app &
```
This command starts the Flask application using Gunicorn with 2 worker processes, binding it to all interfaces on port 8000.

### 6. Run Nginx

```bash
sudo nginx -g "daemon off;"
```
This command starts the Nginx server in the foreground. Make sure you have Nginx installed and properly configured with the `nginx.conf` file provided in the project.
### 7. Access the Application
Open your web browser and navigate to `http://localhost` or `http://your-server-ip` or with `http://domainname` on aws  to see the Flask application running behind Nginx.
## Notes
- Ensure that you have the correct SSL certificates if you are running in production with HTTPS.
- The `run.sh` script is designed for a Linux/Mac environment. If you're using Windows, you may need to adjust the commands accordingly.
- Always remember to deactivate the virtual environment when you're done:
```bash
deactivate
```