# Create a plugin or function that checks for session files in the current directory 
- first if i run `nvim .` and there is a session file, open the session file 
- if open ordinary file and session is in current directory the ask, pop-up 2s

# Presentation for IT Defence
1. influence from usman's presentation

## Slide 2: Cover Page
## Slide 3: Overview
## Slide 4: Introduction
## Slide 5: Organization
## Slide 5: What i Learnt and achieved
## Slide 6: Impact on Organization
## Slide 6: Impact on Training / Responsibilities
### 
## Slide 6: Relevance to my Course
> [!NOTE]
> a seperation between learning and the prove of the learning
> Font size legibility and color
> acknowledge the lecturer and previous course work
> 7/7 rule for powerpoint presentation
## Slide 7: Challenges and Solutions / Recommendations
## Slide 8: Conclusion

# Portfolio Website
## Hero 
## Featured projects
## Technical Skills
## Let's Connect 

# ToDo's
## Setup waydroid for gaming
- Be able to connect bluetooth game Page
- be able to play asphalt 9 and maybe asphalt 8 and maybe epic conquest and be able to manually set pad

## Setup lutris to play games
- download proton 
- donwload some games like devil may cry, silksong, need for speed, pes, 

# Solana Course
- Download roadmap and analyse from youtube
- Download all necessary tutorials from youtube
- setup and start doing projects
- finish watching the videos including the react

-----

# Anchor and Solana Development Environment Setup ⚙️

This guide provides the steps to install **Rust**, the **Solana CLI**, and the **Anchor Framework** on Mac, Linux, or Windows Subsystem for Linux (WSL) to set up your local development environment.

-----

## 1\. Quick Installation (Recommended for Mac/Linux/WSL)

For Mac and Linux (including Windows WSL), you can run a single command to install all major dependencies: Rust, Solana CLI, and Anchor CLI.

> ⚠️ **Windows Users:** You must first install [Windows Subsystem for Linux (WSL)](https://learn.microsoft.com/en-us/windows/wsl/install) (e.g., Ubuntu) and then run this command within the Ubuntu/Linux terminal.

```bash
curl --proto '=https' --tlsv1.2 -sSfL https://solana-install.solana.workers.dev | bash
```

After installation, you should restart your terminal to ensure all **PATH** changes are applied. If the quick install is successful, you can skip to Section 3.

-----

## 2\. Individual Installation Steps

If the quick installation command fails, you can install each dependency individually.

### 2.1. System Dependencies (Linux/WSL Only)

Before installing Rust or the CLIs on a Linux-based system (including WSL), you should install common development tools and necessary packages.

```bash
# 1. Update package lists
sudo apt-get update
# 2. Install dependencies
sudo apt-get install -y \
build-essential \
pkg-config \
libudev-dev llvm libclang-dev \
protobuf-compiler libssl-dev
```

### 2.2. Install Rust 🦀

Solana programs are written in Rust. The recommended installation method is **rustup**.

```bash
# 1. Install Rust
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
# 2. Reload PATH environment variable
. "$HOME/.cargo/env"
# 3. Verify installation
rustc --version
```

### 2.3. Install Solana CLI ⛓️

The Solana CLI provides the tools required to build, deploy, and interact with the network.

```bash
# 1. Install the Solana CLI tool suite
sh -c "$(curl -sSfL https://release.anza.xyz/stable/install)"

# 2. Export PATH (if prompted, or if this is your first install)
export PATH="$HOME/.local/share/solana/install/active_release/bin:$PATH"

# 3. Verify installation
solana --version
```

### 2.4. Install Anchor CLI (Using AVM - Recommended)

The **Anchor Version Manager (AVM)** is the recommended way to install and manage Anchor versions.

```bash
# 1. Install AVM using Rust's package manager (Cargo)
cargo install --git https://github.com/coral-xyz/anchor avm --force

# 2. Install the latest version of Anchor CLI using AVM
avm install latest
avm use latest

# 3. Verify installation
anchor --version
```

### 2.5. Node.js and Yarn (For Testing)

Node.js and Yarn are required to run the default Anchor project test file (which uses TypeScript).

* You can install **Node.js** using a version manager like [nvm](https://github.com/nvm-sh/nvm).
  * Once Node.js is installed, you can install **Yarn** globally: `npm install -g yarn`.

-----

## 3\. Post-Installation Basics

### Solana CLI Configuration

Set your default cluster for development (e.g., to `devnet` or `localhost`).

```bash
# View current config
solana config get

# Set cluster to devnet
solana config set --url devnet
# OR (Short option)
solana config set -ud

# Set cluster to localhost (for local testing)
solana config set -ul
```

### Anchor Project Commands

Once everything is installed, you can start a new project.

```bash
# 1. Initialize a new Anchor project
anchor init <project-name>

# 2. Navigate to the project directory
cd <project-name>

# 3. Build your program
anchor build

# 4. Run tests (This will start a local validator, deploy, and run tests)
anchor test
```

## Language website 
- upload and donwload json data 
- sidebar and toggle for light or dark, word by word, font size and type 
- design and look of the site 
