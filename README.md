\# 🧠 Jetson Orin Nano - Complete Setup \& AI Deployment Guide 🚀



This repository provides a \*\*complete step-by-step guide\*\* for setting up and deploying \*\*AI/ML, vision, and edge computing applications\*\* on the \*\*NVIDIA Jetson Orin Nano\*\*.



Whether you're a beginner or a developer deploying advanced models using \*\*DeepStream\*\*, \*\*Holoscan\*\*, \*\*GXF\*\*, or \*\*Rivermax\*\*, this repository offers everything — from hardware purchase links to software performance optimization.



---



\## 🔧 What's Covered?



\### 🛒 1. Hardware Recommendations \& Purchase Links



To begin working with Jetson Orin Nano, you’ll need the following:



\#### 🧩 Required Components:

| Item | Recommendation | Link |

|------|----------------|------|

| ✅ Jetson Orin Nano Dev Kit | 8GB version recommended | \[Buy from NVIDIA Store](https://developer.nvidia.com/embedded/jetson-orin-nano-devkit) or \[ThinkRobotics](https://thinkrobotics.com/collections/buy-nvidia-jetson-developer-kits-online) |

| ✅ microSD Card | 64GB UHS-I U3 or higher | \[SanDisk Extreme/Ultra recommended](http://www.flipkart.com/sandisk-sdsquab-064g-gn6mn-ultra-64-gb-microsdxc-class-10-140-mb-s-memory-card-compatible-camera-computer-gaming-console-mobile-tablet/p/itm13f1b960bbb9d?pid=ACCGGX76TNFCNDMA\&lid=LSTACCGGX76TNFCNDMAIBPHB3\&marketplace=FLIPKART\&cmpid=content\_memory-card\_8965229628\_gmc) |

| ✅ NVMe SSD (Optional but better) | 256GB–1TB M.2 NVMe (PCIe Gen3 x4) | WD SN350 or WD SN570 |

| ✅ DP (Display Port) to HDMI Converter |

| ✅ USB Keyboard, Mouse, Monitor, HDMI Cable | For initial setup |



---



\### 🖥️ 2. Flashing Jetson OS for First Time Boot (Requires Windows Machine)



\- First, download the JetPack 6.2 or 6.x OS image from \[this link](https://developer.nvidia.com/downloads/embedded/L4T/r36\_Release\_v4.4/jp62-r1-orin-nano-sd-card-image.zip).

\- Then follow the steps below to write the image to a microSD card.



\#### Writing the Image to the microSD Card



You will need a computer with internet access and an SD card reader (either built-in or via adapter).



\##### Instructions for Windows:



\*\*Step 1: Format the microSD Card\*\*  

Use SD Memory Card Formatter from the SD Association.  

!\[My Image](photos/Jetson\_Nano-Getting\_Started-Windows-SD\_Card\_Formatter.png)  

Download, install, and launch the formatter from \[this link](https://www.sdcard.org/downloads/formatter/sd-memory-card-formatter-for-windows-download/).



\- Select the card drive.

\- Choose “Quick format”.

\- Leave “Volume label” blank.

\- Click “Format” to start formatting.

\- Click “Yes” on the warning dialog.



\*\*Step 2: Flash the Image Using Etcher\*\*  

Download, install, and launch Balena Etcher from \[this link](https://etcher.balena.io/).  

!\[My Image](photos/Jetson\_Nano-Getting\_Started-Windows-Etcher.png)



\- Click “Select image” and choose the zipped image file you downloaded earlier.

\- Insert your microSD card (if not already inserted).

\- Click “Select drive” and choose the correct device.  

&nbsp; !\[My Image](photos/Jetson\_Nano-Getting\_Started-Windows-Etcher\_Select\_Drive.png)

\- Click “Flash!”. It will take around 15 minutes to write and validate the image if the card is connected via USB 3.



After flashing, Windows may report that it cannot read the SD card. This is expected — click “Cancel” and remove the microSD card.  

!\[My Image](photos/Jetson\_Nano-Getting\_Started-Windows-SD\_Card\_Prompt.png)







\- Flash OS to NVMe SSD directly \*\*without host PC\*\* using:

&nbsp; - `l4t\_initrd\_flash.sh`

&nbsp; - Jetson’s own U-Boot \& USB storage

\- Optional: Create headless setup using \*\*SSH\*\*, \*\*VNC\*\*



---



\### ⚙️ 3. CUDA, cuDNN, TensorRT Setup

\- Enable and verify \*\*CUDA acceleration\*\*

\- Run GPU tests using \*\*PyTorch\*\* \& TorchScript

\- Tune performance with:

&nbsp; - `sudo nvpmodel -m 2`

&nbsp; - `sudo jetson\_clocks`



---



\### 📦 4. Install AI Frameworks

\- ✅ PyTorch (Jetson-compatible with CUDA)

\- ✅ TensorFlow (JetPack-compatible version)

\- ✅ TorchScript model inference

\- ✅ OpenCV with CUDA and GStreamer support



---



\### 🎥 5. NVIDIA Ecosystem Tools

\- 🔹 \*\*DeepStream SDK\*\* – video analytics \& pipelines

\- 🔹 \*\*Holoscan SDK\*\* – edge medical/robotics compute

\- 🔹 \*\*GXF\*\* – Graph eXecution Framework (Holoscan backend)

\- 🔹 \*\*Rivermax SDK\*\* – high-speed video over 25/100 GbE



---



\### 📊 6. Benchmarks \& Examples

\- OMP (Orthogonal Matching Pursuit) – CPU vs. GPU

\- TorchScript inference times and comparison

\- GPU temperature, frequency, and memory profiling

\- Monitoring tools: `tegrastats`, `jtop`



---



\## 📁 Folder Structure



```



jetson-orin-nano-complete-guide/

├── docs/                      # Setup instructions and images

├── scripts/                   # Bash setup helpers

├── deepstream/                # Sample apps and configs

├── holoscan/                  # Medical/Edge pipeline examples

├── torchscript/               # Model inference \& profiling

├── benchmarks/                # Performance logs and graphs

├── requirements.txt

└── README.md



```



---



\## 🙋 Who Is This For?



\- Developers using Jetson for AI/ML at the edge

\- Students or hobbyists deploying vision projects

\- Researchers working on medical, robotics, or video pipelines

\- Anyone facing challenges setting up Jetson Orin Nano from scratch



---



\## 🛠 Contributions Welcome!

If you've built tools, fixed bugs, or optimized workflows for Jetson Orin Nano — feel free to open a PR!

<!-- Image References -->

\[photos/formatter]: ./photos/Jetson\_Nano-Getting\_Started-Windows-SD\_Card\_Formatter.png

\[photos/etcher]: ./photos/Jetson\_Nano-Getting\_Started-Windows-Etcher.png

\[photos/select-drive]: ./photos/Jetson\_Nano-Getting\_Started-Windows-Etcher\_Select\_Drive.png

\[photos/prompt]: ./photos/Jetson\_Nano-Getting\_Started-Windows-SD\_Card\_Prompt.png







