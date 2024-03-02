After a Fress Install Boot Up with recovary mode and after thet Chenge the Network Repositories to Cloudflare  
```base
kali-tweaks
```

Download Required applications deb files from official sources and install them [Chrome, VS Code, XDM]:

```bash
cd /home/lucifer/Downloads && wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb && wget https://vscode.download.prss.microsoft.com/dbazure/download/stable/019f4d1419fbc8219a181fab7892ebccf7ee29a2/code_1.87.0-1709078641_amd64.deb && wget https://github.com/subhra74/xdm/releases/download/8.0.29/xdman_gtk_8.0.29_amd64.deb && sudo dpkg -i *.deb
```

Make a full upgrade by this Commands

```bash
sudo apt update && sudo apt full-upgrade -y
```

Then Reboot the system

```bash
sudo reboot
```
After start the machine run this command to remove the unwanted programs

```bash
sudo apt remove parole* firefox-esr*
```

Install Curl:

```
sudo apt install curl
```

Now add some important Program's Repositories in the sources.list using this commands

Proton VPN:

```bash
sudo apt install openresolv && sudo wget "https://raw.githubusercontent.com/ProtonVPN/scripts/master/update-resolv-conf.sh" -O "/etc/openvpn/update-resolv-conf" && sudo chmod +x "/etc/openvpn/update-resolv-conf"
```

Docker-ce:

```bash
printf '%s\n' "deb https://download.docker.com/linux/debian bullseye stable" | sudo tee /etc/apt/sources.list.d/docker-ce.list && curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/docker-ce-archive-keyring.gpg
```

VirtualBox:

```bash
curl -fsSL https://www.virtualbox.org/download/oracle_vbox_2016.asc|sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/oracle_vbox_2016.gpg && curl -fsSL https://www.virtualbox.org/download/oracle_vbox.asc|sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/oracle_vbox.gpg && echo "deb [arch=amd64] https://download.virtualbox.org/virtualbox/debian bullseye contrib" | sudo tee /etc/apt/sources.list.d/virtualbox.list
```

Install All Required Applications:

```bash
sudo apt update && sudo apt install -y net-tools fonts-indic conky-all jq moc libu2f-udev gcc g++ openjdk-17-jdk python3-pip python2 burpsuite ffmpeg mugshot bleachbit john nmap gufw xxd preload ttf-mscorefonts-installer celluloid libportaudio2 synaptic ffmpegthumbnailer dkms virtualbox virtualbox-ext-pack docker-ce docker-ce-cli containerd.io metasploit-framework dirbuster nikto hashid libimage-exiftool-perl binwalk steghide wordlists gobuster xsltproc exploitdb hydra wpscan whatweb snapd
```

Download and Install Firefox Stander Version:

```bash
cd /home/lucifer/Downloads && wget https://download-installer.cdn.mozilla.net/pub/firefox/releases/115.0/linux-x86_64/en-US/firefox-115.0.tar.bz2 && tar xjf firefox-*.tar.bz2 && sudo mv firefox /opt && sudo ln -s /opt/firefox/firefox /usr/local/bin/firefox && sudo wget https://raw.githubusercontent.com/mozilla/sumo-kb/main/install-firefox-linux/firefox.desktop -P /usr/local/share/applications
```

<!-- Install haiti:

```bash
sudo gem install haiti-hash
``` -->

Start & Enable All Importaint Services:

```bash
sudo systemctl enable --now bluetooth.service && sudo systemctl enable --now snapd.aa-prompt-listener.service && sudo systemctl enable --now snapd.apparmor.service && sudo systemctl enable --now snapd.recovery-chooser-trigger.service && sudo systemctl enable --now snapd.seeded.service && sudo systemctl enable --now snapd.service && sudo systemctl enable --now snapd.socket && sudo systemctl enable --now snapd.apparmor
```

Install Setup Spotify:

```bash
sudo curl -sS https://download.spotify.com/debian/pubkey_6224F9941A8AA6D1.gpg | sudo gpg --dearmor --yes -o /etc/apt/trusted.gpg.d/spotify.gpg && echo "deb http://repository.spotify.com stable non-free" | sudo tee /etc/apt/sources.list.d/spotify.list && sudo apt-get install spotify-client
```

Install TeamViewer:
```bash
sudo apt install libminizip1 && cd /home/lucifer/Downloads && wget https://download.teamviewer.com/download/linux/teamviewer_amd64.deb && sudo dpkg -i *.deb
```

Then Copy the Desktop Entry:

```bash
sudo cp /var/lib/snapd/desktop/applications/spotify_spotify.desktop /usr/share/applications/
```

Install the pip for python2:

```bash
cd /home/lucifer/Downloads && wget https://bootstrap.pypa.io/pip/2.7/get-pip.py && python2 get-pip.py
```

Add Snap & pip Path in to the PATH:

```bash
# Add Directory into the PATH
export PATH="/home/lucifer/.local/bin:/snap/bin:$PATH"
```

Add this Entry in the .zshrc & .bashrc for the user and the root:

User .zshrc & .bashrc:

```bash
nano /home/lucifer/.zshrc
```
```bash
nano /home/lucifer/.bashrc
```

Root .zshrc & .bashrc:

```bash
sudo nano /root/.zshrc
```
```bash
sudo nano /root/.bashrc
```

Install Telegram:

```bash
cd /home/lucifer/Downloads && wget https://updates.tdesktop.com/tlinux/tsetup.4.8.1.tar.xz && tar -xf tsetup.4.8.1.tar.xz && mkdir /home/lucifer/opt && mv /home/lucifer/Downloads/Telegram /home/lucifer/opt && cd /home/lucifer/opt/Telegram && ./Telegram
```

Settings The <b>lightdm.conf</b> to show username in login screen:

```bash
sudo nano /etc/lightdm/lightdm.conf
```

Then Uncomment the <b>greeter-hide-users=false</b>, <b>user-session=lucifer</b>  
Chenge the user-session to your User Name [In my case it is <i>lucifer</i>]

Chenge the Swappiness value:

```bash
sudo nano /etc/sysctl.conf
```
Then write the line in end of the file:

```bash
vm.swappiness=10
```
Then save this with Ctrl + O and Ctrl + X

Then Use the <b>noatime</b> in the <b>fstab</b>

```bash
sudo nano /etc/fstab
```

Write the <i>noatime,</i> before <i>errors=remount-ro</i>

Download and Install Android Stdio:

```bash
cd /home/lucifer/Downloads && wget https://redirector.gvt1.com/edgedl/android/studio/ide-zips/2022.2.1.20/android-studio-2022.2.1.20-linux.tar.gz && tar -xf android-studio-2022.2.1.20-linux.tar.gz && rm android-studio-2022.2.1.20-linux.tar.gz && mv android-studio/ /home/lucifer/opt && cd /home/lucifer/opt/android-studio/bin && ./studio.sh
```

Install all the Browser Extentions & theme:

```txt
Flagfox, FoxyProxy Standard, Wappalyzer, Dark Reader, Splatoon 2 Colours [Theme]
```

At last Install Extentions for VS Code:

```txt
C/C++, CMake Tools, Extension Pack for Java, Live Server, Prettier - Code formatter, Python
```
