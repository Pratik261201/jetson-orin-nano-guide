\# 🧠 Jetson Orin Nano - Comprehensive Setup \& AI Deployment Guide 🚀



Welcome to this repository — a \*\*complete, step-by-step guide\*\* designed to help you set up and deploy \*\*AI/ML, computer vision, and edge computing applications\*\* on the \*\*NVIDIA Jetson Orin Nano\*\*.



Whether you're a beginner or an experienced developer working with \*\*DeepStream\*\*, \*\*Holoscan\*\*, \*\*GXF\*\*, or \*\*Rivermax\*\*, this guide provides everything you need — from recommended hardware and purchase links to advanced performance optimization tips.



---



\## 🔧 What's Included?



\### 🛒 1. Hardware Recommendations \& Purchase Links



To begin working with the Jetson Orin Nano, the following components are required:



\#### 🧩 Essential Components:



| Item                                       | Recommendation                    | Link                                                                                                                                                                                                                                                                                                                                                    |

| ------------------------------------------ | --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

| ✅ Jetson Orin Nano Dev Kit                 | 8GB version recommended           | \[Buy from NVIDIA Store](https://developer.nvidia.com/embedded/jetson-orin-nano-devkit) or \[ThinkRobotics](https://thinkrobotics.com/collections/buy-nvidia-jetson-developer-kits-online)                                                                                                                                                                |

| ✅ microSD Card                             | 64GB UHS-I U3 or higher           | SanDisk Extreme/Ultra recommended (\[Flipkart Link](http://www.flipkart.com/sandisk-sdsquab-064g-gn6mn-ultra-64-gb-microsdxc-class-10-140-mb-s-memory-card-compatible-camera-computer-gaming-console-mobile-tablet/p/itm13f1b960bbb9d?pid=ACCGGX76TNFCNDMA\&lid=LSTACCGGX76TNFCNDMAIBPHB3\&marketplace=FLIPKART\&cmpid=content\_memory-card\_8965229628\_gmc)) |

| ✅ NVMe SSD \*(Optional but Recommended)\*    | 256GB–1TB M.2 NVMe (PCIe Gen3 x4) | WD SN350 or WD SN570                                                                                                                                                                                                                                                                                                                                    |

| ✅ DisplayPort to HDMI Adapter              |                                   |                                                                                                                                                                                                                                                                                                                                                         |

| ✅ USB Keyboard, Mouse, Monitor, HDMI Cable | Required for initial setup        |                                                                                                                                                                                                                                                                                                                                                         |



---



\### 🖥️ 2. Flashing Jetson OS for Initial Boot (Windows Machine Required)



1\. \*\*Download the OS Image (JetPack 6.2 or 6.x)\*\*

&nbsp;  Get it from this link:

&nbsp;  \[Jetson JetPack OS Image](https://developer.nvidia.com/downloads/embedded/L4T/r36\_Release\_v4.4/jp62-r1-orin-nano-sd-card-image.zip)



2\. \*\*Write the Image to microSD Card\*\*

&nbsp;  You'll need a Windows PC with internet access and an SD card reader (built-in or via USB).



\#### Step-by-step Instructions:



\*\*A. Format the microSD Card\*\*

Use \[SD Memory Card Formatter](https://www.sdcard.org/downloads/formatter/sd-memory-card-formatter-for-windows-download/) by the SD Association.

!\[Formatter](photos/Jetson\_Nano-Getting\_Started-Windows-SD\_Card\_Formatter.png)



\* Launch the tool.

\* Select the appropriate drive.

\* Choose “Quick format.”

\* Leave the “Volume label” field blank.

\* Click “Format,” and confirm by clicking “Yes” on the warning dialog.



\*\*B. Flash the Image Using Balena Etcher\*\*

Download \[Balena Etcher](https://etcher.balena.io/) and install it.

!\[Etcher Launch](photos/Jetson\_Nano-Getting\_Started-Windows-Etcher.png)



\* Open Etcher.

\* Click \*\*“Select Image”\*\* and choose the downloaded ZIP file.

\* Insert the microSD card.

\* Click \*\*“Select Drive”\*\* and choose the correct card reader.

&nbsp; !\[Select Drive](photos/Jetson\_Nano-Getting\_Started-Windows-Etcher\_Select\_Drive.png)

\* Click \*\*“Flash!”\*\*

&nbsp; The flashing and validation process may take \\~15 minutes, especially over USB 3.0.



After completion, Windows may display a prompt saying it cannot read the SD card. This is expected — simply click \*\*Cancel\*\* and safely eject the card.

!\[SD Card Prompt](photos/Jetson\_Nano-Getting\_Started-Windows-SD\_Card\_Prompt.png)



---



Let me know if you’d like this version exported as a `.md` file or need help writing sections for DeepStream, Holoscan, or performance tuning!







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





