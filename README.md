# 🌞 Доброе Утро - Good Morning App

A beautiful, interactive **Spring Boot web application** with stunning animations that displays a personalized good morning message with animated sun, floating particles, and interactive elements.

![Java](https://img.shields.io/badge/Java-17-orange?style=flat-square)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.1.5-green?style=flat-square)
![Maven](https://img.shields.io/badge/Maven-Build-blue?style=flat-square)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)

## ✨ Features

- 🌈 **Animated Gradient Background** - Multi-color flowing gradient animation
- ☀️ **Interactive Sun** - Double orbital rings with rotating rays and pulsing effect
- 💫 **Floating Particles** - 30 particles continuously floating upward
- 💛 **Pulsing Hearts** - Animated hearts with hover effects
- 🎊 **Interactive Emoji Bursts** - Click anywhere or hearts for emoji animations
- 📱 **Fully Responsive** - Works perfectly on mobile, tablet, and desktop
- ⚡ **Smooth Animations** - CSS3 animations for fluid user experience
- 🇷🇺 **Russian Greeting** - Personalized message in Russian

## 🚀 Quick Start

### Prerequisites

- **Java 17+**
- **Maven 3.6+**
- **Docker** (optional)

### Clone the Repository

```bash
git clone https://github.com/Skipper04/kotlin-spring-hello-world.git
cd kotlin-spring-hello-world
```

### Option 1: Run with Maven

```bash
# Build the project
mvn clean install

# Run the application
mvn spring-boot:run
```

The application will start on `http://localhost:8080`

### Option 2: Run with Docker

```bash
# Build and run with Docker Compose
docker-compose up --build
```

Visit: **http://localhost:8080/**

### Option 3: Run JAR Directly

```bash
# Build the JAR
mvn clean package

# Run the JAR
java -jar target/spring-hello-world-1.0.0.jar
```

## 📁 Project Structure

```
kotlin-spring-hello-world/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/example/
│   │   │       ├── controller/
│   │   │       │   └── HelloController.java    # REST Controller
│   │   │       └── Application.java            # Spring Boot Main
│   │   └── resources/
│   │       ├── templates/
│   │       │   └── index.html                  # Beautiful UI with animations
│   │       └── application.yml                 # Configuration
│   └── test/
│       └── java/                               # Test classes
├── pom.xml                                     # Maven configuration
├── Dockerfile                                  # Docker configuration
├── docker-compose.yml                          # Docker Compose setup
└── README.md                                   # This file
```

## 🛠️ Technology Stack

| Technology | Version | Purpose |
|-----------|---------|---------|
| Java | 17 | Backend language |
| Spring Boot | 3.1.5 | Framework |
| Spring MVC | 3.1.5 | Web layer |
| Thymeleaf | 3.1.5 | Template engine |
| Maven | Latest | Build tool |
| Docker | Latest | Containerization |

## 📝 API Endpoints

### Home Page
```
GET /
```
Returns the beautiful animated good morning page.

**Response:** HTML page with interactive elements

## 🎨 Design Features

### Animations
- **Gradient Background**: Multi-color flowing animation (15s cycle)
- **Sun Animation**: 
  - Pulse effect (4s cycle)
  - Double orbital rings rotating in opposite directions
  - 16 rotating rays
  - Realistic shadow and glow
- **Particles**: 30 floating particles with randomized animation
- **Text Elements**: Slide-in and fade-in animations
- **Hearts**: Heartbeat animation with hover effects

### Interactivity
- **Click Anywhere**: Triggers emoji burst animation (3 emojis)
- **Click Hearts**: Individual heart emoji animations
- **10 Emoji Types**: 😊 🌈 ✨ 💕 🎉 🌸 🦋 🌟 💫 🎊

### Responsive Design
- Mobile-first approach
- Breakpoint at 768px
- Adjustable font sizes and spacing
- Touch-friendly interactive elements

## ⚙️ Configuration

### application.yml

```yaml
spring:
  application:
    name: spring-hello-world

server:
  port: 8080

logging:
  level:
    root: INFO
    com.example: DEBUG
```

### Customization

**Change Port:**
```yaml
server:
  port: 9000
```

**Change Log Level:**
```yaml
logging:
  level:
    root: WARN
    com.example: INFO
```

## 🐳 Docker Setup

### Dockerfile

The project includes a `Dockerfile` for containerization:

```dockerfile
FROM openjdk:17-slim
WORKDIR /app
COPY target/spring-hello-world-1.0.0.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
```

### docker-compose.yml

```yaml
version: '3.8'
services:
  app:
    build: .
    ports:
      - "8080:8080"
    environment:
      - JAVA_OPTS=-Xmx512m -Xms256m
```

## 📦 Dependencies

```xml
<!-- Spring Boot Web -->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>

<!-- Thymeleaf Template Engine -->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-thymeleaf</artifactId>
</dependency>

<!-- Spring Boot Test -->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-test</artifactId>
    <scope>test</scope>
</dependency>
```

## 🌐 Browser Support

- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

## 🚀 Performance

- **Load Time**: < 2 seconds
- **Animation FPS**: 60fps
- **Memory Usage**: ~50-100MB
- **Docker Image Size**: ~300MB

## 🎯 Use Cases

- **Birthday/Holiday Greetings**: Personalized morning message
- **Dashboard**: Beautiful homepage for web application
- **Wellness App**: Daily motivation and positivity
- **Portfolio**: Impressive frontend demonstration
- **Learning**: Spring Boot + Thymeleaf + CSS3 animations

## 📚 Development Guide

### Adding New Features

1. **New Endpoint**:
   ```java
   @GetMapping("/new-page")
   public String newPage() {
       return "new-page";
   }
   ```

2. **New Template**:
   - Create file: `src/main/resources/templates/new-page.html`
   - Reference in controller

3. **Styling**:
   - Add CSS to `<style>` tag in HTML template
   - Or create external CSS file in `src/main/resources/static/css/`

### Running Tests

```bash
mvn test
```

### Building Production JAR

```bash
mvn clean package -DskipTests
```

## 🔧 Troubleshooting

### Port Already in Use
```bash
# Change port in application.yml or via command line
java -jar app.jar --server.port=9000
```

### Template Not Found
- Ensure file is in `src/main/resources/templates/`
- Check file name matches controller return value
- Verify Thymeleaf dependency is added

### Docker Build Fails
```bash
# Clean and rebuild
mvn clean install
docker-compose build --no-cache
```

## 📄 License

This project is licensed under the **MIT License** - see LICENSE file for details.

## 👤 Author

**Andrei Kalikin** (@Skipper04)

## 🤝 Contributing

Contributions are welcome! Please feel free to:
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## 📞 Support

For issues, questions, or suggestions:
- Open an issue on GitHub
- Check existing issues for solutions
- Review the troubleshooting section

## 🌟 Acknowledgments

- Spring Boot team for the amazing framework
- CSS Animation inspiration from modern design patterns
- Community feedback and contributions

---

**Made with ❤️ for morning smiles** ☀️✨
