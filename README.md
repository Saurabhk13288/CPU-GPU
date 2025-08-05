# CPU-GPU

Yes, **the OpenCL code will work** on an **Intel Core i9 x86 system with an NVIDIA GPU running Ubuntu**, **as long as the OpenCL drivers and runtime for your GPU are properly installed**.

### ✅ What you need:

1. **NVIDIA GPU with CUDA support**.
2. **Install NVIDIA drivers** (e.g., `nvidia-driver-XXX`).
3. **Install NVIDIA OpenCL ICD loader**:

   ```bash
   sudo apt update
   sudo apt install ocl-icd-libopencl1 nvidia-opencl-dev
   ```
4. **Verify OpenCL platforms** using:

   ```bash
   clinfo
   ```

   If you see your NVIDIA GPU listed as a platform/device, you're good to go.

---

### ❌ What *won’t* work:

If OpenCL drivers or ICD (Installable Client Drivers) are **not installed**, the GPU portion of the program will **fail silently or crash**. So `clinfo` is your best first test.

---

### ⚠️ Caveat:

On **MacBook Air M1/M2** with Ubuntu installed via virtualization (e.g., UTM, Parallels, or Asahi Linux), OpenCL support is **limited or non-existent**, because:

* Apple's M-series GPU is not supported by standard OpenCL drivers on Linux.
* You may need **Metal API** on macOS for native GPU acceleration, not OpenCL.

---

If you want, I can tailor the setup steps and code for your **i9 + NVIDIA on Ubuntu** system or help troubleshoot `clinfo` output.
