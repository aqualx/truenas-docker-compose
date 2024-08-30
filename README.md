## truenas-docker-compose

This repository provides meticulously crafted Docker Compose files for deploying a range of applications on your TrueNAS SCALE server. Leverage the power of Nvidia GPUs (e.g., Tesla) for enhanced performance and AI capabilities. 

**Prerequisites:**

* **TrueNAS Scale 24.04 (Dragonfish):**
   * Set up sandboxes with Jailmaker: [TrueNAS Scale: Setting up Sandboxes with Jailmaker](https://youtu.be/S0nTRvAHAP8)
* **TrueNAS Scale 24.10 (Electric Eel) and up:**
    * Migrate sandboxes to Docker: [TrueNAS Scale: Migrating Sandboxes to Docker in Electric Eel // Compose, Dockge & Jailmaker](https://youtu.be/R0Vdj1culo0)


**Current Applications:**

* **Home Assistant (HA):** 
    * A comprehensive setup with mariadb, mosquitto, zigbee2mqtt, hass-configurator, nodered, and influxdb.
* **Ollama + open-webui:**  Harness the power of Ollama for personalized AI experiences.
* **Nextcloud:** The latest release includes the latest ffmpeg package and `go-vod` for hardware video transcoding in Memories applications, ensuring smooth performance.
* **Vaultwarden:** Securely manage your passwords with a self-hosted Bitwarden solution.

**Folder Structure:**

* **`apps/`:** Individual application folders containing:
    * `docker-compose.yml`:  Docker Compose configuration tailored for each application.
    * `.env`: Environment variables specific to the application.
* **`apps/dockerfiles/`:** Custom Dockerfile configurations for optimized images.

**Key Features:**

* **Nvidia GPU Support:** All docker-compose files are meticulously configured to leverage Nvidia GPUs (e.g., Tesla) for enhanced performance and AI capabilities. 
* **Optimized Performance:**  Dockerfiles are tailored for TrueNAS Scale, ensuring efficient resource utilization. 

**Important Notes:**

* **Environment Variables (`USER_ID`, `GROUP_ID`, `TIMEZONE}`, etc.):** Create users/groups for rootless docker usage within your TrueNAS Scale and set them in your `.env` files according to your configuration.
* **Data Directories (`DATA_DIR`):** Define the path to your shared data directory (e.g., `/mnt/storage/docker`) where applications will store their persistent data  and set them in your `.env` files according to your configuration.
* **Network Configuration:** Adjust network settings within `compose.yaml` as needed for your TrueNAS Scale environment.

Let me know if you have any questions or need further assistance!