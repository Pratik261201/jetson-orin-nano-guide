* **Jetson Orin Nano** is supported for the latest **DeepStream 7.x** ✅
* Now have access to **next-gen performance** with **TensorRT 9**, **CUDA 12**, and **Jetson Linux 36.x** → turning your Orin Nano into a true **AI edge supercomputer** 🚀

---

### ✅ **Steps to Install DeepStream 7.x on JetPack 6.0 / 6.2**

> 📌 DeepStream 7.x is supported officially on JetPack 6.x
> Source: [NVIDIA DeepStream 7.x Release Notes](https://docs.nvidia.com/metropolis/deepstream/dev-guide/text/DS_Release_Notes.html)

---

### **Step 1: Update your system**

```bash
sudo apt update
sudo apt upgrade -y
```

---

### **Step 2: Add NVIDIA SDK Repository (JetPack 6.x already includes it)**

> You can skip this in most JetPack 6.x installs, but if needed:

```bash
sudo apt-key adv --fetch-keys https://repo.download.nvidia.com/jetson/jetson-ota-public.asc
```

---

### **Step 3: Install DeepStream 7.0 (latest available as of JetPack 6.2)**

```bash
sudo apt install deepstream
```

This will install the latest version available (DeepStream 7.0 or 7.1 depending on availability in the JetPack 6.2 repo).

---

### **Step 4: Test Your Installation**

```bash
cd /opt/nvidia/deepstream/deepstream-7.0
deepstream-app -c samples/configs/deepstream-app/source1_usb_dec_infer_resnet_int8.txt
```

---

### **Step 5: (Optional) Add Environment Variables**

Add this to your `~/.bashrc` to make CLI usage easier:

```bash
export PATH=$PATH:/opt/nvidia/deepstream/deepstream-7.0/bin
export LD_LIBRARY_PATH=/opt/nvidia/deepstream/deepstream-7.0/lib:$LD_LIBRARY_PATH
export GST_PLUGIN_PATH=/opt/nvidia/deepstream/deepstream-7.0/lib/gst-plugins:$GST_PLUGIN_PATH
```

Then apply:

```bash
source ~/.bashrc
```

---

### 🧠 You're Now Ready to Use Your Jetson as an Edge AI Supercomputer!

DeepStream 7.x + JetPack 6.2 turns your Jetson into a **powerful real-time AI video analytics system**, optimized for:

* YOLOv8, SSD, Faster-RCNN, etc.
* Multi-stream 4K inference
* Edge deployment and analytics

