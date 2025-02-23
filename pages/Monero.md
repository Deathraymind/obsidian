# Ubuntu
- Got it! Here's how you can install and set up **XMRig** on Ubuntu:
  
  ---
- ### **Step 1: Update Your System**
  
  Before installing, update your packages:
  
  ```
  sudo apt update && sudo apt upgrade -y
  ```
  
  ---
- ### **Step 2: Install Required Dependencies**
  
  ```
  sudo apt install git build-essential cmake libuv1-dev libssl-dev libhwloc-dev -y
  ```
  
  ---
- ### **Step 3: Clone and Build XMRig**
  
  ```
  git clone https://github.com/xmrig/xmrig.git
  cd xmrig
  mkdir build && cd build
  cmake ..
  make -j$(nproc)
  ```
  
  This compiles XMRig using all available CPU cores.
  
  ---
- ### **Step 4: Configure XMRig**
- Create a config file:
  
  ```
  nano config.json
  ```
- Add a mining pool (e.g., **SupportXMR**):
  
  ```
  {
  "autosave": true,
  "cpu": true,
  "pools": [
    {
      "url": "pool.hashvault.pro:443",
      "user": "YOUR_MONERO_WALLET_ADDRESS",
      "pass": "x",
      "keepalive": true,
      "tls": true
    }
  ]
  }
  ```
- Save the file (`CTRL+X`, then `Y`, then `Enter`).
  
  ---
- ### **Step 5: Start Mining**
  
  Run XMRig with:
  
  ```
  ./xmrig
  ```
  
  ---
- ### **Step 6: Monitor Mining Performance**
  
  To see your mining progress:
  
  ```
  htop   # Monitor CPU usage
  ```
- ### Go Too https://monero.hashvault.pro/en/dashboard