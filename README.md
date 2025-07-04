# 🧠 Jetson Orin Nano - Complete Setup & AI Deployment Guide 🚀

This repository provides a **complete step-by-step guide** for setting up and deploying **AI/ML, vision, and edge computing applications** on the **NVIDIA Jetson Orin Nano**.

Whether you're a beginner or a developer deploying advanced models using **DeepStream**, **Holoscan**, **GXF**, or **Rivermax**, this repository offers everything — from hardware purchase links to software performance optimization.

---

## 🔧 What's Covered?

### 🛒 1. Hardware Recommendations & Purchase Links

To begin working with Jetson Orin Nano, you’ll need the following:

#### 🧩 Required Components:
| Item | Recommendation | Link |
|------|----------------|------|
| ✅ Jetson Orin Nano Dev Kit | 8GB version recommended | [Buy from NVIDIA Store](https://developer.nvidia.com/embedded/jetson-orin-nano-devkit) or [ThinkRobotics](https://thinkrobotics.com/collections/buy-nvidia-jetson-developer-kits-online) |
| ✅ microSD Card | 64GB UHS-I U3 or higher | [SanDisk Extreme/Ultra recommended](http://www.flipkart.com/sandisk-sdsquab-064g-gn6mn-ultra-64-gb-microsdxc-class-10-140-mb-s-memory-card-compatible-camera-computer-gaming-console-mobile-tablet/p/itm13f1b960bbb9d?pid=ACCGGX76TNFCNDMA&lid=LSTACCGGX76TNFCNDMAIBPHB3&marketplace=FLIPKART&cmpid=content_memory-card_8965229628_gmc) |
| ✅ NVMe SSD (Optional but better) | 256GB–1TB M.2 NVMe (PCIe Gen3 x4) | WD SN350 or WD SN570 |
| ✅ DP (Display Port) to HDMI Converter |
| ✅ USB Keyboard, Mouse, Monitor, HDMI Cable | For initial setup |

---

### 🖥️ 2. Flashing Jetson OS for First Time Boot (Requires Windows Machine)

- First, download the JetPack 6.2 or 6.x OS image from [this link](https://developer.nvidia.com/downloads/embedded/L4T/r36_Release_v4.4/jp62-r1-orin-nano-sd-card-image.zip).
- Then follow the steps below to write the image to a microSD card.

#### Writing the Image to the microSD Card

You will need a computer with internet access and an SD card reader (either built-in or via adapter).

##### Instructions for Windows:

**Step 1: Format the microSD Card**  
Use SD Memory Card Formatter from the SD Association.  
![Image](https://github.com/Pratik261201/jetson-orin-nano-guide/blob/main/photos/Jetson_Nano-Getting_Started-Windows-SD_Card_Formatter.png)
Download, install, and launch the formatter from [this link](https://www.sdcard.org/downloads/formatter/sd-memory-card-formatter-for-windows-download/).

- Select the card drive.
- Choose “Quick format”.
- Leave “Volume label” blank.
- Click “Format” to start formatting.
- Click “Yes” on the warning dialog.

**Step 2: Flash the Image Using Etcher**  
Download, install, and launch Balena Etcher from [this link](https://etcher.balena.io/).  
![My Image](photos/Jetson_Nano-Getting_Started-Windows-Etcher.png)

- Click “Select image” and choose the zipped image file you downloaded earlier.
- Insert your microSD card (if not already inserted).
- Click “Select drive” and choose the correct device.  
  ![My Image](photos/Jetson_Nano-Getting_Started-Windows-Etcher_Select_Drive.png)
- Click “Flash!”. It will take around 15 minutes to write and validate the image if the card is connected via USB 3.

After flashing, Windows may report that it cannot read the SD card. This is expected — click “Cancel” and remove the microSD card.  
![My Image](photos/Jetson_Nano-Getting_Started-Windows-SD_Card_Prompt.png)

## ⚙️ Setup and First Boot

Once your microSD card is ready, proceed with setting up the Jetson Orin Nano Developer Kit.

### 🧾 Setup Steps

1. Insert the microSD card (with the flashed system image) into the slot located on the underside of the Jetson Orin Nano module.
2. Power on your monitor or display and connect it to the developer kit.
3. Connect the USB keyboard and mouse.
4. Plug in the power supply provided with the kit.  
   The Jetson Orin Nano Developer Kit will automatically power on and begin the boot process.

![My Image](photos/jetson-orin-nano-dev-kit-sd-slot.jpg)

---

### 🚀 First Boot

A green LED near the USB-C connector will light up once the board powers on. During the first boot, you will be guided through the initial configuration steps:

- Review and accept the NVIDIA Jetson Software EULA.
- Select your preferred system language, keyboard layout, and time zone.
- Connect to a Wi-Fi network.
- Create a username, password, and hostname.
- Log in to your new Jetson environment.

---

### 🖥️ After Logging In

Once logged in, you’ll see the following screen — congratulations on setting up your Jetson Orin Nano!

![My Image](photos/Getting_started-Jetson_Xavier_NX-screenshot.png)

---
Sure! Here's the rephrased version:

---

### 💽 Flash the OS Directly to NVMe SSD (No Host PC Needed)

**Supported NVMe SSDs**: WD SN350 or WD SN570 recommended

You can install the operating system directly onto your NVMe SSD using the Jetson device itself—no separate host computer is required. This process utilizes Jetson’s built-in **U-Boot** and **USB boot** capabilities.

Navigate to the following directory within this GitHub repository:
📁 `boot-from-ssd`

This approach makes use of the Jetson’s native tools to flash the OS directly via USB and U-Boot.

---

### 💻 Optional: Headless Setup

For remote setup and control without a connected display or keyboard/mouse:

- Use **SSH** for terminal-based remote access.
- Use **VNC** for full desktop environment over the network.

---

## 🚀 Unlocking Super Performance Mode

The default power mode of Jetson Orin Nano is set to **25W**. To unlock the full hardware potential, you can switch to the **MAXN SUPER** mode.

bash```
sudo jetson_clocks
### 🔋 Steps to Enable MAXN SUPER Mode

1. On the Ubuntu desktop, locate the **NVIDIA icon** on the top-right panel.
2. Click on the icon to open the **Power Mode** menu.
3. From the options, select **MAXN SUPER** to activate maximum performance mode.

![My Image](photos/jons_power-mode-to-maxn-super.png)


### ⚙️ 3. CUDA, cuDNN, TensorRT Setup
- Enable and verify **CUDA acceleration**
- Run GPU tests using **PyTorch** & TorchScript
- Tune performance with:
  - `sudo nvpmodel -m 2`
  - `sudo jetson_clocks`

---

### 📦 4. Install AI Frameworks
- ✅ PyTorch (Jetson-compatible with CUDA)
- ✅ TensorFlow (JetPack-compatible version)
- ✅ TorchScript model inference
- ✅ OpenCV with CUDA and GStreamer support

---

### 🎥 5. NVIDIA Ecosystem Tools
- 🔹 **DeepStream SDK** – video analytics & pipelines
- 🔹 **Holoscan SDK** – edge medical/robotics compute
- 🔹 **GXF** – Graph eXecution Framework (Holoscan backend)
- 🔹 **Rivermax SDK** – high-speed video over 25/100 GbE
---

## 📁 Folder Structure

```

jetson-orin-nano-complete-guide/
├── docs/                      # Setup instructions and images
├── scripts/                   # Bash setup helpers
├── deepstream/                # Sample apps and configs
├── holoscan/                  # Medical/Edge pipeline examples
├── torchscript/               # Model inference & profiling
├── benchmarks/                # Performance logs and graphs
├── migrate-jetson-to-ssd/     # To Boot OS from SSD
├── JetsonChat/                # Offline AI CHATBOT to TEST GPU performance 
├── requirements.txt
└── README.md

```

---

## 🙋 Who Is This For?

- Developers using Jetson for AI/ML at the edge
- Students or hobbyists deploying vision projects
- Researchers working on medical, robotics, or video pipelines
- Anyone facing challenges setting up Jetson Orin Nano from scratch

---

## 🛠 Contributions Welcome!
If you've built tools, fixed bugs, or optimized workflows for Jetson Orin Nano — feel free to open a PR!

<!-- Image References -->
[photos/formatter]: ./photos/Jetson_Nano-Getting_Started-Windows-SD_Card_Formatter.png
[photos/etcher]: ./photos/Jetson_Nano-Getting_Started-Windows-Etcher.png
[photos/select-drive]: ./photos/Jetson_Nano-Getting_Started-Windows-Etcher_Select_Drive.png
[photos/prompt]: ./photos/Jetson_Nano-Getting_Started-Windows-SD_Card_Prompt.png


