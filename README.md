# Docker Commands and Setup Instructions

## Docker CLI Commands

### Show Docker Images
```bash
docker images
```

### Build Docker Image
```bash
docker build -t basic-app .
```

### Build Docker Image with class Libary
# add example 
## D:\OneDrive - intellier.com\project\JustPractice\WebApplication1\WebApplication1\Dockerfile
## D:\OneDrive - intellier.com\project\JustPractice\WebApplication1\WebApplication2\Dockerfile
## D:\OneDrive - intellier.com\project\JustPractice\WebApplication1\ClassLibrary1   --class libary
```bash
D:\OneDrive - intellier.com\project\JustPractice\WebApplication1>
      docker build -f "D:\OneDrive - intellier.com\project\JustPractice\WebApplication1\WebApplication1\Dockerfile" --tag test "D:\OneDrive - intellier.com\project\JustPractice\WebApplication1"
```

### Run Docker Container
```bash
docker run --name basic-app-container-v2 -p 44378:5194 basic-app2
```

## Docker Compose Commands

### Create Image File
```bash
docker-compose build
```

### Run Containers
```bash
docker-compose up
```

### Build and Run Together
```bash
docker-compose up --build
```

## Notes
- **Check `docker-compose.override.yml` File**
- **Ensure Correct Port Configuration**

## Docker Installation Steps

1. Download Docker for Windows.
2. Enable required Windows features:
   - **Hyper-V**
   - **Virtual Machine Platform**
   - **Windows Hypervisor Platform**
   - **Windows Subsystem for Linux (WSL)**
3. Open `cmd` or `PowerShell` as Administrator.
4. Verify WSL installation:
   ```bash
   wsl --status
   ```
5. Update WSL:
   ```bash
   wsl --update
   ```
6. Set WSL default version to 2:
   ```bash
   wsl --set-default-version 2
   
