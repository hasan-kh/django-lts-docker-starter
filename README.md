# Django 5.2 LTS Template

![Docker](https://img.shields.io/badge/docker-ready-blue)
![GitLab CI](https://img.shields.io/badge/gitlab-ci%2Fcd-blueviolet)
![Python](https://img.shields.io/badge/python-3.12+-informational)
![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)

A fully-featured Django 5.2 LTS project template that includes a custom user model with endpoints, JWT authentication, admin two-factor authentication, centralized logging and error handling, and request throttling. The project follows CI/CD best practices using GitLab and is fully dockerized for consistent development and deployment.

## 🚀 How to Use This Template

1. Click the green **“Use this template”** button at the top of the repo.
2. Create your new project repository from the template.
3. Clone your new project:
   ```bash
   git clone https://github.com/hasan-kh/django-lts-docker-starter.git
   cd django-lts-docker-starter

## ⚙️ Features

- **Admin Two-Factor Authentication**: Enable OTP (One-Time Password) for the Django admin via environment variables.
- **JWT Authentication**: Secure login mechanism using JSON Web Tokens.
- **OpenAPI Documentation**: Auto-generated API docs with drf-spectacular.
- **Centralized Error Handling**: Unified and structured error responses.
- **Custom Logging**: Colored, human-readable logs with user ID and IP address.
- **Email Notifications for Errors**: Critical errors are emailed to administrators.
- **Internationalization**: Includes English and Farsi, extendable to other languages.
- **Request Throttling**: API rate limiting with customizable scopes.
- **Asynchronous Tasks**: Celery-based background task queue with priority support.
- **CI/CD with GitLab**: Automated linting, testing, building, and deployment.
- **Dockerized**: All services containerized for scalability and ease of use.

## 🛠 Tech Stack

- **Backend**: Django & Django REST Framework
- **Database**: PostgreSQL
- **API Documentation**: drf-spectacular (OpenAPI Schema)
- **Task Queue**: Celery & RabbitMQ
- **Scheduler**: Celery Beat
- **Monitoring**: Flower
- **Cache**: Redis
- **Web Server**: Nginx
- **Containerization**: Docker & Docker Compose
- **CI/CD**: GitLab CI/CD

## 🧰 Installation

### Prerequisites
- Docker & Docker Compose
- GitLab Runner (optional, for CI/CD pipeline execution)

### Steps

1. Clone the repository:
   ```sh
   git clone https://gitlab.com/hasankhodadadi97/tabdeal
   cd template5.2
   ```

2. Generate environment files from templates in the `envs` directory:
   ```sh
   make create-env-files
   ```

3. Build the application services:
   ```sh
   make build
   ```

4. Start the services:
   ```sh
   make up
   ```

5. Create a superuser (optional):
   ```sh
   docker compose exec app python manage.py createsuperuser
   ```

## 💡 Usage

### Access
- Swagger API Docs: [http://localhost:8000/api/docs/](http://localhost:8000/api/docs/)
- Django Admin Panel: [http://localhost:8000/admin/](http://localhost:8000/admin/)
- Flower Monitoring Dashboard: [http://localhost:5555/](http://localhost:5555/)
- RabbitMQ Dashboard: [http://localhost:15672/](http://localhost:15672/)

### Run linter
```sh
make lint
```
OR
```sh
docker compose exec app sh -c "cd /app && sh ./scripts/lint.sh"
```
### Run Tests
```sh
make test
```
OR
```sh
docker compose exec app sh -c "cd /app/core && python manage.py test"
```

## 🔁 CI/CD Workflow
- GitLab CI/CD automatically builds Docker images and pushes them to the GitLab Container Registry.
- On successful pushes, deployment pipelines update running containers.
- Modify the `Makefile` as needed:
  - Replace `LOCAL_APP_IMAGE_NAME` with your preferred Docker image name.
  - Replace `DEPLOY_DIR_BASE` with your target deployment directory.

## 🧾 Makefile Help
You can view available `make` commands by running:
```sh
make help
```

## 🤝 Contributing
1. Fork the repository.
2. Create a new branch: `git checkout -b feature-name`
3. Commit and push your changes: `git push origin feature-name`
4. Open a merge request on GitLab.

## License
MIT License

