# Flask Blog Website

A simple, responsive blog platform built with Flask as part of Dr. Angela Yu’s "100 Days of Code: The Complete Python Pro Bootcamp". Users can read posts, register, log in, create/edit/delete their own posts, and leave comments.

---

## Table of Contents

1. [Features](#features)
2. [Demo](#demo)
3. [Prerequisites](#prerequisites)
4. [Installation](#installation)
5. [Configuration](#configuration)
6. [Project Structure](#project-structure)
7. [Usage](#usage)
8. [Customization](#customization)
9. [Deployment](#deployment)
10. [Credits](#credits)
11. [License](#license)

---

## Features

- **User Authentication**: Secure registration and login with hashed passwords.
- **Blog Posts**: CRUD operations for posts (Create, Read, Update, Delete).
- **Comments**: Authenticated users can comment on posts.
- **Admin Controls**: Admin user can manage all posts and comments.
- **Responsive Design**: Mobile-friendly layout using Bootstrap.
- **Rich Text Editing**: Integrated WYSIWYG editor for post content.

---

## Demo

![Blog Demo](./demo/demo.gif)

Live demo: [https://your-blog-app.herokuapp.com](https://your-blog-app.herokuapp.com)

---

## Prerequisites

- Python 3.7+
- pip
- Virtual environment tool (venv, virtualenv)

---

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/flask-blog.git
   cd flask-blog
   ```

2. **Create and activate virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate    # macOS/Linux
   venv\\Scripts\\activate   # Windows
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Initialize the database**
   ```bash
   flask shell
   >>> from app import db
   >>> db.create_all()
   >>> exit()
   ```

---

## Configuration

Copy `config_example.py` to `config.py` and update the following environment variables:

```python
SECRET_KEY = '<your-secret-key>'
SQLALCHEMY_DATABASE_URI = 'sqlite:///blog.db'
ADMIN_EMAIL = 'admin@example.com'
ADMIN_PASSWORD = '<secure-password>'
```

For production, you can use PostgreSQL or MySQL by setting the appropriate URI.

---

## Project Structure

```
flask-blog/
├── app/
│   ├── __init__.py       # Initialize Flask app
│   ├── models.py         # Database models: User, Post, Comment
│   ├── routes.py         # URL routes and view functions
│   ├── forms.py          # WTForms classes for login, post creation, comments
│   ├── static/           # CSS, JS, images
│   └── templates/        # Jinja2 templates
├── config_example.py     # Example config file
├── requirements.txt      # Python package dependencies
├── demo/                 # Demo assets (GIF, screenshots)
├── run.py                # Entry point to start the server
└── README_Blog_Website.md
```

---

## Usage

1. **Start the server**
   ```bash
   flask run
   ```
2. **Open your browser** at `http://127.0.0.1:5000`

3. **Create an admin account** via CLI or register on the site.
4. **Start blogging!**

---

## Customization

- **Themes**: Swap Bootstrap CDN links in `base.html` or use custom CSS in `static/style.css`.
- **Editor**: Replace default WYSIWYG with another one (e.g., Quill, CKEditor).
- **Email Notifications**: Integrate Flask-Mail to notify users of comments or new posts.

---

## Deployment

1. **Heroku**:
   - Create a new Heroku app: `heroku create`
   - Provision a database (Postgres): `heroku addons:create heroku-postgresql:hobby-dev`
   - Push code: `git push heroku main`
   - Set config vars on Heroku dashboard.
   - Run migrations: `heroku run flask shell` → `db.create_all()`

2. **Other Platforms**: Dockerfile included for containerization.

---

## Credits

- Dr. Angela Yu – Course content and guidance.
- Flask community – Excellent documentation and extensions.

---

## License

This project is released under the MIT License. See the [LICENSE](LICENSE) file for details.

