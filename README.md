<div align="center">

# 🏔️ ExploreWithUs

### Discover the History side of Maharashtra

Beautiful forts, hidden trails and unforgettable adventures, now packaged in a Docker container so it runs the same everywhere.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)

</div>

---

## 📸 Preview

<!-- Add a screenshot of the site at assets/screenshot.png, then keep this line -->
![ExploreWithUs home page](assets/screenshot.png)

---

## 📖 About

**ExploreWithUs** is a travel website that helps people discover forts and treks across Maharashtra. The site has these sections:

| Section | Purpose |
|---|---|
| 🏠 **Home** | Introduction and call-to-action buttons (*Explore Treks*, *Find My Trek*) |
| 🥾 **Treks** | Browse trekking destinations |
| 🏰 **Forts** | Explore the historic forts of Maharashtra |
| 🧭 **Find Your Trek** | Help visitors find a trek that suits them |
| 👥 **Community** | Connect with fellow trekkers |

This repository also doubles as a **hands-on DevOps practice project**: a static website containerised with **Docker**, served by **nginx** and started with **Docker Compose**.

---

## 🗂️ Project Structure

```text
ExploreWithUS/
├── index.html      # Page structure
├── style.css       # Colours and layout
├── script.js       # Interactivity
├── README.md       # You are here
├── Dockerfile      # Recipe to build the container image
└── compose.yml     # One-command startup with Docker Compose
```

---

## 🚀 Quick Start

### Option 1: Run with Docker (recommended)

**Prerequisites:** [Docker](https://docs.docker.com/get-docker/) and Docker Compose.

```bash
# 1. Clone the repository
git clone https://github.com/Avishkar5658/ExploreWithUS.git
cd ExploreWithUS

# 3. Start the container
docker-compose up -d
```

Now open **http://localhost** in your browser. 🎉

> On a cloud playground such as Killercoda, open port **80** from the traffic/ports menu to get a public link.

**Stop everything:**

```bash
docker-compose down
```

### Option 2: Run without Docker

The site is plain HTML, CSS and JavaScript, so you can simply open `index.html` in your browser.

---

## 🐳 How the Docker Setup Works

### `Dockerfile`: the recipe

```dockerfile
FROM nginx:latest
COPY . /usr/share/nginx/html
```

1. Start from the official **nginx** web server image.
2. Copy the website files into the folder nginx serves to visitors.

### `compose.yml`: the order slip

```yaml
services:
  web:
    image: explorewithus:v1
    ports:
      - "80:80"
```

- `web` is the name of the service.
- `image` uses the image built in the quick start.
- `ports: "80:80"` maps port 80 of your machine to port 80 of the container.

### Big picture

```text
 Dockerfile  ──build──▶  Image  ──compose up──▶  Container (nginx + site)  ──▶  Browser
  (recipe)            (packed meal)               (meal being served)
```

---

## 🛠️ Useful Commands

| Command | What it does |
|---|---|
| `docker images` | List images on your machine |
| `docker ps` | List running containers |
| `docker logs <container>` | View container output |
| `docker-compose up -d` | Start in the background |
| `docker-compose down` | Stop and remove the containers |

---

## 🧯 Troubleshooting

<details>
<summary><b><code>service 'image' must be a mapping not a string</code></b></summary>

In `compose.yml`, `image:` must sit **under a service name** (such as `web:`), not directly under `services:`. Check your indentation: use spaces, not tabs.

</details>

<details>
<summary><b><code>pull access denied for web1 ... repository does not exist</code></b></summary>

Docker could not find the image name locally, so it tried to download it from Docker Hub. Make sure the `image:` value in `compose.yml` exactly matches an image shown by `docker images`.

</details>

---

## 🎯 What I Learned

- Writing a `Dockerfile` and building an image
- Serving a static site with **nginx**
- Defining and running services with **Docker Compose**
- Reading and fixing real Docker and YAML errors
- Testing on a Linux (Ubuntu) playground

---

## 🗺️ Roadmap

- [ ] Add a screenshot gallery
- [ ] Add more treks and forts
- [ ] Publish the image to Docker Hub
- [ ] Add a CI/CD pipeline with GitHub Actions
- [ ] Deploy on AWS

---

## 👤 Author

**Avishkar Thorave**
B.E. Artificial Intelligence and Data Science, Pune, aspiring Cloud and DevOps engineer.

[![GitHub](https://img.shields.io/badge/GitHub-Avishkar5658-181717?style=flat&logo=github)](https://github.com/Avishkar5658)

---

<div align="center">

⭐ If you like this project, give it a star!

</div>
