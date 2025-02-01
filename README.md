Here’s a clean and well-formatted version of your Docker commands:

---

### 🚀 **Docker Commands Cheat Sheet**

#### ✅ **Check Docker Version**  
```bash
docker --version
```

#### 🏗️ **Build Docker Image**  
```bash
docker build -t <image_name>:<tag> .
# Example:
docker build -t dockerdemoapp:v1 .
```

#### ▶️ **Run Docker Container with Port Mapping**  
```bash
docker run --name <container_name> -p <host_port>:<container_port> <image_name>:<tag>
# Example:
docker run --name my-node-app -p 3000:3000 dockerdemoapp:v1
```

#### 📋 **List Running Containers**  
```bash
docker ps
```

#### 📦 **List All Docker Images**  
```bash
docker images
```

#### ❌ **Stop or Kill a Running Container**  
```bash
docker stop <container_name_or_id>
docker kill <container_name_or_id>
```

#### 🗑️ **Remove a Container**  
```bash
docker rm <container_name_or_id>
```

---

### 🔗 **Bind Mount (Sync Local Project with Container)**  
```bash
docker run --name <container_name> -p <host_port>:<container_port> -v <local_path>:<container_path> <image_name>:<tag>
# Example:
docker run --name my-node-app-2 -p 5000:3000 -v C:\Users\saite\source\Docker_Demo:/user/src/app dockerdemoapp:v2
```

#### 🚫 **Sync Local Project While Excluding `node_modules`**  
```bash
docker run --name <container_name> -p 3000:3000 \
  -v /usr/src/app/node_modules \
  -v $(pwd):/user/src/app <image_name>:<tag>
```

---

### 💻 **Access Running Container (Interactive Mode)**  
- **For Linux:**  
  ```bash
  docker exec -it <container_name> sh
  ```

- **For Windows (PowerShell):**  
  ```bash
  docker exec -it <container_name> cmd
  ```

---

### 📦 **Create a Build for Development Environment**  
```bash
docker build -t <image_name>:<tag> -f Dockerfile.dev .
# Example:
docker build -t dockerdemoapp:v3 -f Dockerfile.dev .
```

---

This format should be easier to read and reference. Let me know if you'd like any modifications! 🚀
