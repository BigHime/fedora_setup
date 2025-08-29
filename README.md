# 🚀 تهيئة فيدورا بعد التثبيت (للألعاب والبرمجة)

## 📌 1. تحديث النظام
```bash
sudo dnf update -y
```

## 📌 2. تفعيل مستودعات RPM Fusion
```bash
sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```

## 📌 3. تثبيت الكوديكات ووسائط التشغيل
```bash
sudo dnf group install multimedia --setopt=install_weak_deps=False --exclude=PackageKit-gstreamer-plugin
sudo dnf group install sound-and-video
```

## 📌 4. أدوات أساسية
```bash
sudo dnf install vim git curl wget htop gnome-tweaks gparted
```

## 📌 5. Flatpak + Flathub
```bash
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

## 🎮 إعداد فيدورا للألعاب

### 1. تعريفات كروت الشاشة
- NVIDIA:
```bash
sudo dnf install akmod-nvidia
```
- AMD/Intel:
```bash
sudo dnf install mesa-dri-drivers mesa-vulkan-drivers
```

### 2. منصات الألعاب
```bash
sudo dnf install steam lutris
flatpak install flathub com.heroicgameslauncher.hgl
```

### 3. تحسين الأداء
```bash
sudo dnf install gamemode
```
ثم أضف في خيارات تشغيل اللعبة (Steam):
```
gamemoderun %command%
```

### 4. دعم يد التحكم
```bash
sudo dnf install joystick
```

---

## 💻 إعداد فيدورا للبرمجة

### 1. أدوات التطوير الأساسية
```bash
sudo dnf group install "Development Tools" "Development Libraries"
```

### 2. لغات برمجة شائعة
```bash
# Python
sudo dnf install python3 python3-pip ipython

# C / C++
sudo dnf install gcc g++ gdb cmake make

# Java
sudo dnf install java-21-openjdk-devel maven

# Node.js
sudo dnf install nodejs npm

# Rust
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# Go
sudo dnf install golang
```

### 3. محررات IDEs
- VS Code (Flatpak):
```bash
flatpak install flathub com.visualstudio.code
```
- JetBrains Toolbox:
```bash
flatpak install flathub com.jetbrains.Toolbox
```

### 4. الحاويات (Containers)
- Podman (موصى به من فيدورا):
```bash
sudo dnf install podman buildah
```
- أو Docker:
```bash
sudo dnf install docker docker-compose
sudo systemctl enable --now docker
```

### 5. قواعد البيانات
```bash
# PostgreSQL
sudo dnf install postgresql postgresql-server

# MariaDB (بديل MySQL)
sudo dnf install mariadb-server

# SQLite (عادة مثبت مسبقاً)
sudo dnf install sqlite
```

---

✅ بعد تنفيذ هذه الخطوات، سيكون لديك نظام فيدورا مجهز بالكامل للألعاب والبرمجة.
