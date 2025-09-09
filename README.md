# Super Mario Bros - Browser Game

A fully functional Super Mario Bros game built with TypeScript, HTML5 Canvas, and modern web technologies. This game runs entirely in the browser and includes classic Mario mechanics like jumping, enemy stomping, coin collection, and platform physics.



## 🙌 Credits

Original game code: https://github.com/iam-veeramalla/super-mario-mimic

DevOps containerization and cloud deployment: Santosh reddy

# 🎮 Super Mario Mimic – Dockerized & Deployed on Azure

This project is an open-source **Super Mario mimic game** built with **Node.js**.  
My **DevOps contribution** was to debug, containerize, and successfully deploy the application on an **Azure Virtual Machine** using Docker.  

---

## 🔧 My DevOps Contribution

- Created an **optimized multi-stage Dockerfile** (see [`devops/Dockerfile`](./devops/Dockerfile)).  
- Fixed build issues (`node:18-alphine` → `node:18-alpine`).  
- Built and ran the container locally with Docker.  
- Deployed on an **Azure Ubuntu VM**.  
- Configured **Azure NSG rules** to expose port 8080.  
- Resolved **Docker daemon permission issues** (`/var/run/docker.sock`).  
I started by creating an Azure VM and SSH’d into it using my private key. Once inside, I installed Docker and configured the environment. After cloning the repository, I noticed it didn’t have a Docker setup suitable for optimization, so I created my own Dockerfile inside a devops/ folder.

I used a multi-stage Docker build to first install dependencies and build the project, and then created a lightweight production image using node:18-alpine. This approach helped me reduce the image size compared to a single-stage build, which is an important DevOps practice for efficiency and faster deployments.

Once the image was built, I ran the container and exposed it on port 8080. Finally, I verified that the Mario Game was accessible through the browser, served via http-server.

---

## 🛠️ Tech Stack

- **Application**: Node.js, JavaScript, HTML, CSS  
- **DevOps Tools**: Docker, Azure VM (Ubuntu), Linux, Networking  

---

## 🚀 How to Run

### 1️⃣ Clone the repo
```bash
git clone https://github.com/<your-username>/super-mario-mimic.git
cd super-mario-mimic

2️⃣ Build the image
docker build -t mario-game -f devops/Dockerfile .

3️⃣ Run the container
docker run -p 8080:8080 mario-game

4️⃣ Access in browser
http://localhost:8080

On Azure VM (replace <vm-ip> with your public IP):
http://<vm-ip>:8080

My deployed azure vm
http://20.0.83.247:8080/


### 1. Docker Build
![Docker Build](./images/Screenshot%20\(89\).png)

### 2. Mario Game in Browser
![Mario Game](./images/Screenshot%20\(92\).png)
![Mario Game](./images/Screenshot%20\(93\).png)

### 3. My Virtual Machine
![VM](./images/Screenshot%20\(91\).png)



## 💡 Key Learnings

Worked with multi-stage Docker builds for smaller image sizes.

Understood cloud networking: firewall + NSG rules in Azure.

Solved real-world issues like missing images, build typos, and permission errors.

Gained hands-on experience in end-to-end DevOps workflow:
clone → containerize → deploy → expose → access via browser.

👨‍💻 Author: Santosh reddy
🔗 LinkedIn: https://www.linkedin.com/in/santosh-reddy-95a342283



