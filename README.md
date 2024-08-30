## truenas-docker-compose: Power Up Your TrueNAS SCALE Server

This repository houses meticulously crafted Docker Compose files designed to effortlessly deploy a suite of powerful applications on your TrueNAS SCALE server. Take advantage of Nvidia GPUs (e.g., Tesla) for accelerated performance and unlock the potential of AI with dedicated containers. 

**Prerequisites:**

* **TrueNAS Scale 24.04 (Dragonfish):**
   * Set up sandboxes with Jailmaker: [TrueNAS Scale: Setting up Sandboxes with Jailmaker](https://youtu.be/S0nTRvAHAP8)
* **TrueNAS Scale 24.10 (Electric Eel) and up:**
    * Native Docker: [TrueNAS Scale: Migrating Sandboxes to Docker in Electric Eel // Compose, Dockge & Jailmaker](https://youtu.be/R0Vdj1culo0)


**Current Applications:**

* **[Home Assistant (HA)](https://github.com/home-assistant):** 
    * A comprehensive setup with mariadb, mosquitto, zigbee2mqtt, hass-configurator, nodered, and influxdb.
* **[Ollama](https://github.com/ollama/ollama) + [open-webui](https://github.com/open-webui/open-webui):**  Harness the power of Ollama for personalized AI experiences.
* **[Nextcloud](https://github.com/nextcloud):** The latest release includes the latest ffmpeg package and `go-vod` for hardware video transcoding in Memories applications, ensuring smooth performance.
* **[Vaultwarden](https://github.com/dani-garcia/vaultwarden):** Securely manage your passwords with a self-hosted Bitwarden solution.

**Folder Structure:**

* **`apps/`:** Individual application folders containing:
    * `docker-compose.yml`:  Docker Compose configuration tailored for each application.
    * `.env`: Environment variables specific to the application.
* **`apps/dockerfiles/`:** Custom Dockerfile configurations for optimized images.

**Key Features:**

* **Nvidia GPU Support:** All docker-compose files are meticulously configured to leverage Nvidia GPUs (e.g., Tesla) for enhanced performance and AI capabilities. 
* **Optimized Performance:**  Dockerfiles are tailored for TrueNAS Scale, ensuring efficient resource utilization. 

**Example of a hardware where this can be run:**

* **[HP Microserver Gen 8](https://h20427.www2.hpe.com/pdf/HP_ProLiant_MicroServer_Gen8_quicspec.pdf):**
    * CPU: [Intel(R) Xeon(R) CPU E3-1265L V2](https://ark.intel.com/content/www/us/en/ark/products/65728/intel-xeon-processor-e3-1265l-v2-8m-cache-2-50-ghz.html)
    * Memory: 16Gb ECC
    * GPU: [NVidia Tesla P4 8Gb](https://www.techpowerup.com/gpu-specs/tesla-p4.c2879) or [NVidia Tesla T4 16Gb](https://www.techpowerup.com/gpu-specs/tesla-t4.c3316)

**Important Notes:**

* **Environment Variables (`USER_ID`, `GROUP_ID`, `TIMEZONE`, etc.):** Create users/groups for rootless docker usage within your TrueNAS Scale and set them in your `.env` files according to your configuration.
* **Data Directories (`DATA_DIR`):** Define the path to your shared data directory (e.g., `/mnt/storage/docker`) where applications will store their persistent data  and set them in your `.env` files according to your configuration.
* **Network Configuration:** Adjust network settings within `compose.yaml` as needed for your TrueNAS Scale environment.

Let me know if you have any questions or need further assistance!