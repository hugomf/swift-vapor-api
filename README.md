# Swift Vapor API

A modern, scalable API built with Swift Vapor framework featuring MongoDB integration and Docker containerization.

## 🚀 Features

- **Swift Vapor 4** - High-performance server-side Swift web framework
- **MongoDB Integration** - MongoDB Swift driver for database operations
- **Docker Support** - Containerized development and production deployment
- **RESTful API** - Clean, structured API endpoints
- **Testing Ready** - XCTest framework integration

## 📋 Prerequisites

- **Swift 5.6+** - [Install Swift](https://www.swift.org/install/)
- **Docker** (optional) - [Install Docker](https://docs.docker.com/get-docker/)
- **MongoDB** (optional) - Local or cloud instance

## 🛠️ Installation

### 1. Clone the Repository

```bash
git clone <your-repo-url>
cd swift-vapor-api
```

### 2. Install Dependencies

```bash
swift package resolve
```

### 3. Build the Project

```bash
swift build
```

## 🏃‍♂️ Running the Application

### Development Mode

```bash
swift run
```

The server will start on `http://localhost:8080`

### Production Mode

```bash
swift run --configuration release
```

## 🐳 Docker Deployment

### Build the Docker Image

```bash
docker-compose build
```

### Run with Docker Compose

```bash
docker-compose up app
```

### Run in Background

```bash
docker-compose up -d app
```

### Stop the Container

```bash
docker-compose down
```

## 📊 API Endpoints

### Base URL: `http://localhost:8080`

| Method | Endpoint | Description | Response |
|--------|----------|-------------|----------|
| `GET` | `/` | Health check | `"It works!"` |
| `GET` | `/hello` | Hello world | `"Hello, world!"` |

## 🧪 Testing

Run the test suite:

```bash
swift test
```

## 🗃️ Project Structure

```
swift-vapor-api/
├── Sources/
│   ├── App/
│   │   ├── configure.swift    # Application configuration
│   │   ├── routes.swift       # Route definitions
│   │   └── Controllers/       # API controllers
│   └── Run/
│       └── main.swift         # Application entry point
├── Tests/
│   └── AppTests/             # Test files
├── Public/                   # Static files
├── Package.swift             # Swift package manifest
├── Dockerfile               # Docker container configuration
└── docker-compose.yml       # Docker compose configuration
```

## 🔧 Configuration

### Environment Variables

The application supports the following environment variables:

- `LOG_LEVEL` - Logging level (default: `debug`)
- `DATABASE_URL` - MongoDB connection string (if configured)

### MongoDB Setup

To use MongoDB with this application:

1. Install MongoDB locally or use a cloud service like MongoDB Atlas
2. Set the connection string in your environment:
   ```bash
   export DATABASE_URL="mongodb://localhost:27017/your-database"
   ```

## 📦 Dependencies

- **Vapor** (`4.0.0+`) - Web framework
- **MongoSwift** (`0.1.3+`) - MongoDB driver

## 🚢 Deployment

### Heroku

```bash
# Create a Heroku app
heroku create your-app-name

# Set buildpack for Swift
heroku buildpacks:set https://github.com/vapor-community/heroku-buildpack

# Deploy
git push heroku main
```

### DigitalOcean App Platform

1. Connect your repository
2. Set build command: `swift build -c release`
3. Set run command: `Run serve --env production --hostname 0.0.0.0 --port $PORT`

### AWS/Google Cloud

Use the provided Dockerfile to build and deploy containers to your preferred cloud platform.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a pull request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Troubleshooting

### Common Issues

**Port already in use:**
```bash
# Kill process on port 8080
lsof -ti:8080 | xargs kill
```

**Docker build fails:**
```bash
# Clean Docker cache
docker system prune
docker-compose build --no-cache
```

**Swift package resolve issues:**
```bash
# Clean and rebuild
swift package clean
swift package resolve
```

## 📚 Resources

- [Vapor Documentation](https://docs.vapor.codes/)
- [Swift Package Manager](https://swift.org/package-manager/)
- [MongoDB Swift Driver](https://github.com/mongodb/mongo-swift-driver)
- [Docker Documentation](https://docs.docker.com/)

## 🙏 Acknowledgments

- [Vapor Community](https://vapor.codes/) for the excellent web framework
- [MongoDB](https://www.mongodb.com/) for the Swift driver
- [Swift Server Working Group](https://swift.org/server/) for server-side Swift guidance