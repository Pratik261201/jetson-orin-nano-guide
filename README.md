\# 🧠 Jetson Orin Nano - Comprehensive Setup \& AI Deployment Guide 🚀



This repository serves as a \*\*complete step-by-step guide\*\* for setting up and deploying \*\*AI/ML, computer vision, and edge computing applications\*\* on the \*\*NVIDIA Jetson Orin Nano\*\*.



Whether you're a beginner or an experienced developer working with \*\*DeepStream\*\*, \*\*Holoscan\*\*, \*\*GXF\*\*, or \*\*Rivermax\*\*, this guide equips you with everything you need — from hardware recommendations and purchase links to performance tuning for your AI applications.



---



\## 🔧 What's Included?



\### 🛒 1. Hardware Recommendations \& Purchase Links



To get started with the Jetson Orin Nano, the following components are required:



\#### 🧩 Essential Components:

| Item | Recommendation | Link |

|------|----------------|------|

| ✅ Jetson Orin Nano Dev Kit | 8GB version recommended | \[Buy from NVIDIA Store](https://developer.nvidia.com/embedded/jetson-orin-nano-devkit) / \[ThinkRobotics](https://thinkrobotics.com/collections/buy-nvidia-jetson-developer-kits-online) |

| ✅ microSD Card | 64GB UHS-I U3 or higher | \[SanDisk Extreme/Ultra recommended](http://www.flipkart.com/sandisk-sdsquab-064g-gn6mn-ultra-64-gb-microsdxc-class-10-140-mb-s-memory-card-compatible-camera-computer-gaming-console-mobile-tablet/p/itm13f1b960bbb9d) |

| ✅ NVMe SSD \*(Optional but Recommended)\* | 256GB–1TB M.2 NVMe (PCIe Gen3 x4) | WD SN350 or WD SN570 |

| ✅ DP (DisplayPort) to HDMI Converter |

| ✅ USB Keyboard, Mouse, Monitor, HDMI Cable | Required for initial setup |



---



\### 🖥️ 2. Flashing Jetson OS for Initial Boot (Windows Machine Required)



1\. \*\*Download the OS Image (JetPack 6.2 or 6.x)\*\*  

&nbsp;  \[Download JetPack Image](https://developer.nvidia.com/downloads/embedded/L4T/r36\_Release\_v4.4/jp62-r1-orin-nano-sd-card-image.zip)



2\. \*\*Write the Image to microSD Card\*\*  

&nbsp;  You will need a Windows computer with an internet connection and an SD card reader (built-in or via USB).



\#### Step-by-Step Instructions:



---



\*\*A. Format the microSD Card\*\*  

Use the official \[SD Memory Card Formatter](https://www.sdcard.org/downloads/formatter/sd-memory-card-formatter-for-windows-download/).



!\[SD Card Formatter](photos/Jetson\_Nano-Getting\_Started-Windows-SD\_Card\_Formatter.png)



\- Launch the tool.

\- Select the correct SD card drive.

\- Choose \*\*Quick format\*\*.

\- Leave the \*\*Volume label\*\* field blank.

\- Click \*\*Format\*\*, then confirm by clicking \*\*Yes\*\* on the warning prompt.



---



\*\*B. Flash the OS Image Using Balena Etcher\*\*  

Download and install \[Balena Etcher](https://etcher.balena.io/).



!\[Etcher - Launch](photos/Jetson\_Nano-Getting\_Started-Windows-Etcher.png)



\- Open Etcher.

\- Click \*\*“Select Image”\*\* and choose the downloaded zipped image file.

\- Insert your microSD card.

\- Click \*\*“Select Drive”\*\* and choose the appropriate device.



!\[Etcher - Select Drive](photos/Jetson\_Nano-Getting\_Started-Windows-Etcher\_Select\_Drive.png)



\- Click \*\*“Flash!”\*\*  

&nbsp; Flashing and validation may take approximately 15 minutes over USB 3.0.



Once completed, Windows may display a prompt indicating it cannot read the SD card. This is expected. Simply click \*\*Cancel\*\* and safely remove the microSD card.



!\[Windows SD Card Prompt](photos/Jetson\_Nano-Getting\_Started-Windows-SD\_Card\_Prompt.png)







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





