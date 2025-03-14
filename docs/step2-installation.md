# Step 2: Installation & Setup on Linux Mint

Hey everyone! In this step, I’m walking you through setting up my Linux Mint environment for molecular docking. Linux Mint is great—it's lightweight, user-friendly, and perfect for running the tools we need.

## What You'll Need
- **Linux Mint:** Make sure you’re running a proper installation.
- **AutoDock Tools & AutoDock Vina:** These are the main tools I’m using.
- **Python & Bash:** I’ll be using these for some automation and scripting.
- **Internet Connection:** For downloading packages and tools.

## Step-by-Step Setup

### 1. Update Your System
Open your terminal and run:
```bash
sudo apt update && sudo apt upgrade
```
This ensures everything is up-to-date.

### 2. Install AutoDock Tools and Vina
For AutoDock Vina, you can try installing via apt:
```bash
sudo apt install autodock-vina
```
For AutoDock Tools, download it from the official site if it’s not available in the package manager. Follow the instructions provided on their website.

### 3. Verify Python Installation
Check your Python version:
```bash
python3 --version
```
If you need Python 3:
```bash
sudo apt install python3
```

### 4. Set Up Your Workspace
Create a neat directory structure:
```bash
mkdir -p ~/docking_project/{docs,notebooks,scripts,data}
```
This helps keep everything organized.

## Wrapping Up
That’s it for the installation part! I tried to keep things simple. If you run into any issues, drop a note in the repo’s issues section. Next up, we’ll run our first docking experiment!
