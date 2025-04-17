# NetData-Task
**Task-7## ✅ TASK 7: Monitor System Resources Using Netdata**


**🧠 Netdata in Simple Terms:**  

Netdata is a free, real-time **performance and health monitoring tool** for your computers, servers, and applications. It helps you see what’s happening inside your system **instantly**, like:  

- **CPU, RAM, and Disk Usage** – How much your system is working.  
- **Network Traffic** – How much data is being sent/received.  
- **Running Applications** – Which programs are using resources.  
- **Alerts** – Notifies you if something is wrong (e.g., high CPU usage).  

### **Why is Netdata Special?**  
1. **Real-time** – Updates every second (unlike many tools that update every few minutes).  
2. **Easy Setup** – Just install it, and it works instantly in your web browser.  
3. **No Heavy Config Needed** – Automatically detects and monitors many services (like databases, web servers, etc.).  
4. **Lightweight** – Uses very little CPU/RAM, so it doesn’t slow down your system.  

### **Who Uses Netdata?**  
- **System Admins** – To keep servers healthy.  
- **Developers** – To debug performance issues.  
- **Home Users** – To check why their PC is slow.  

📊 How does it show the data?
It has a beautiful web dashboard that displays graphs and charts updating in real time.
So you can instantly see if something is going wrong or using too many resources.


---


### 🎯 **Objective**
Install and run Netdata to monitor **system resources and app performance metrics**, using Docker.

---

### 🧰 **Tools Needed**
- **Netdata** (Real-time monitoring tool)
- **Docker** (To run Netdata easily without installing directly)

---

### 🧭 **Steps to Complete the Task**

#### 1. ✅ **Run Netdata Using Docker**
🐳 What is Docker? Docker is a containerization platform that lets you package apps and their dependencies into containers — lightweight, standalone units that run consistently across environments.

⚙️ Key Concepts:

Term What It Means Image A blueprint for a container — includes code, dependencies, OS libs Container A running instance of an image — isolated, fast, and lightweight Dockerfile A script with instructions to build your own Docker image Docker Hub A public repository for images (like GitHub but for Docker)


****
**✅ Why Docker is Useful Portable: Runs the same on dev, staging, prod****
**

Lightweight: Shares the host kernel; faster than VMs

Isolated: Each container runs independently

Fast Deployment: Instant boot-up of pre-built environments

Perfect for Monitoring: You can run tools like Netdata in a container, avoiding manual setup

we should directly copy paste this link in the instance

**
**🔗 wget -O /tmp/netdata-kickstart.sh https://get.netdata.cloud/kickstart.sh && sh /tmp/netdata-kickstart.sh --nightly-channel
****

**we also use tools like prometheus and Grafana ABOUT PROMETHEUS AND GRAFANA**

📡 Prometheus – Monitoring & Metrics Collection Prometheus is a time-series database and monitoring system developed by SoundCloud. It scrapes metrics from targets (apps, systems, services) at specified intervals and stores them with timestamps.

**🔍 What Prometheus Does: Scrapes metrics from endpoints like /metrics**

Stores them efficiently as time-series data

Allows querying with its own language: PromQL

Can trigger alerts via Alertmanager

✅ Typical Targets: Linux servers

Docker containers

Kubernetes pods

Applications (with exporters)

📊 Grafana – Beautiful Dashboards for Your Metrics Grafana is a visualization and dashboarding tool that can connect to many data sources, including Prometheus.

🎨 What Grafana Does: Queries metrics from Prometheus (or others like InfluxDB, Loki)

Displays metrics as interactive graphs, charts, tables

Supports alerts, variables, templating

Offers pre-built dashboards for many services

🔁 Together: Prometheus + Grafana = 👌

Tool Role Prometheus Collects and stores metrics (e.g., CPU, memory, app stats) Grafana Visualizes those metrics beautifully with charts and dashboards
Open your terminal and run this command:


```bash
docker run -d --name=netdata -p 19999:19999 --cap-add SYS_PTRACE --security-opt apparmor=unconfined netdata/netdata
```

> This command:
> - Downloads the Netdata container
> - Runs it in the background (`-d`)
> - Exposes the dashboard at port `19999`
> - Adds permissions needed for full monitoring

---

#### 2. 🌐 **Access the Netdata Dashboard**
- Open your browser and go to:
  ```
  http://localhost:19999
  ```

You’ll see a **real-time dashboard** showing:
- **CPU usage**
- **Memory usage**
- **Disk activity**
- **Network stats**
- **Docker container metrics** (if any running)

---

#### 3. 📊 **Explore the Dashboard**
- Click on different sections:
  - **"System Overview"** → for CPU, memory, etc.
  - **"Disk"** → for I/O activity
  - **"Docker"** → if you have containers running
- Look at the **Alerts** and **Health Notifications**

---

#### 4. 🔍 **Check Netdata Logs (Optional)**
To see logs for Netdata (helpful for troubleshooting):

```bash
docker exec -it netdata bash
cd /var/log/netdata
ls
```

You can view logs using:
```bash
cat error.log
```

---

### 📸 **Deliverables**
- **Screenshot** of the Netdata dashboard (you can use Snipping Tool, Snip & Sketch, or `PrtSc` on your keyboard)
- Make sure it shows live metrics like CPU, RAM, and maybe Docker if you're using containers

---

### 🧠 **Outcome**
After completing this:
- You’ll know how to **monitor servers and applications** using Netdata
- You'll understand how **real-time metrics** help you detect issues early
- You'll experience **lightweight and fast monitoring** through Docker

---
![Screenshot (81)](https://github.com/user-attachments/assets/d400630d-7477-46d3-ab62-e03061605878)

![Screenshot (48)](https://github.com/user-attachments/assets/5c886dfd-1e17-4eb3-bfb5-e616de36f449)

![Screenshot (50)](https://github.com/user-attachments/assets/e94c7297-c702-4d05-b35c-462715446904)

![Screenshot (51)](https://github.com/user-attachments/assets/f2ff6bf8-5b83-444d-823f-6d53bc16526f)

![Screenshot (52)](https://github.com/user-attachments/assets/fccc892b-84a6-4ea9-ae50-e8daeb71eb25)
![Screenshot (54)](https://github.com/user-attachments/assets/6419afed-48ea-4793-8486-b377333def82)

![Screenshot (55)](https://github.com/user-attachments/assets/136363fc-1502-423b-a8d3-31b5855f1546)


![Screenshot (56)](https://github.com/user-attachments/assets/f14f4fc2-807e-48c8-919c-5ec7754fd301)
![Screenshot (57)](https://github.com/user-attachments/assets/5a60dc27-831e-4043-b9c0-fbd7898978d0)

![Screenshot (62)](https://github.com/user-attachments/assets/9720f9b9-85f7-4ee1-86cd-ef42f9527d22)
![Screenshot (72)](https://github.com/user-attachments/assets/3adff3ce-1b82-4aa4-a3ae-a834907ef912)


![Screenshot (66)](https://github.com/user-attachments/assets/fc273e62-c6a5-484e-a189-c7f51be52a41)

![Screenshot (74)](https://github.com/user-attachments/assets/c432f48f-1b3d-4c45-9ef7-4d05cc7872c2)

![Screenshot (58)](https://github.com/user-attachments/assets/845ff0dc-b2b4-483a-8b32-2cc724718809)

