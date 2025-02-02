# Skill Share Platform

## Overview
Skill Share is a platform where individuals can connect with others within their region to exchange skills. Users can either barter their skills with others or, if they lack a skill to trade, use tokens to compensate the other party. The platform also includes a review system to ensure credibility and quality of exchanges.

## Features
- **Skill Exchange**: Users can offer their skills in exchange for other skills.
- **Token System**: If a user does not have a skill to trade, they can use tokens as a form of compensation.
- **Review System**: Users can leave reviews for each other after a skill exchange to build trust and credibility.
- **User Authentication**: Secure authentication using JWT.
- **Database Management**: Uses SQLAlchemy with Alembic for migrations.

## Tech Stack
- **Backend**: FastAPI
- **Database**: SQLAlchemy
- **Migrations**: Alembic
- **Authentication**: JWT-based authentication
- **Logging & Utilities**: Custom logging and utility functions for handling data processing

## Project Structure
```
app/
├── config/                # Configuration files
├── core/
│   ├── admin/             # Admin-related functionalities
│   ├── auth/              # Authentication system (JWT, password hashing, etc.)
│   ├── notification/      # Notifications system
│   ├── reviews/           # Review management
│   ├── skill_share/       # Main skill-sharing functionality
│   ├── skills/            # Skills management
│   ├── users/             # User management
├── utils/
│   ├── crud/              # CRUD operations
│   ├── logger/            # Logging system
│   ├── types_utils/       # Utility types for the project
│   ├── crypto.py          # Encryption and decryption utilities
│   ├── password_hash.py   # Password hashing utilities
│   ├── my_jwt.py          # JWT handling
│   ├── response_message.py# Standardized response messages
│   ├── query.py           # Query helpers
│   ├── regex.py           # Regular expressions utilities
│   ├── upload_handler.py  # File upload handling
│   ├── uuid_generator.py  # UUID generation
├── versions/              # Database migration versions
```

## Installation & Setup

### Prerequisites
- Python 3.9+
- PostgreSQL (or any preferred SQL database)
- Virtual environment (recommended)

### Setup Instructions
#### 1. Clone the Repository
```sh
git clone https://github.com/your-repo/skill-share.git
cd skill-share
```
#### 2. Create a Virtual Environment & Activate It
```sh
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

#### 3. Install Dependencies
```sh
pip install -r requirements.txt
```

#### 4. Configure Environment Variables
Create a `.env` file in the project root and add:
```env
DATABASE_URL=postgresql://user:password@localhost/skillshare_db
SECRET_KEY=your_secret_key
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30
```

#### 5. Apply Migrations
```sh
alembic upgrade head
```

#### 6. Run the Development Server
```sh
uvicorn app.main:app --reload
```
Or using the provided command:
```sh
make fastapi-dev
```

### API Documentation
Once the server is running, you can access the API documentation at:
- **Swagger UI**: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
- **Redoc**: [http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc)

## Contributing
1. Fork the repository.
2. Create a new branch.
3. Make your changes and commit them.
4. Push to your fork and submit a pull request.

## License
This project is licensed under the MIT License.

## Contact
For any questions or support, reach out to [your-email@example.com].

