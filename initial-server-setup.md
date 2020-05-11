# DigitalOcean ၌ Ubuntu Setup လုပ်ရာတွင် အခြေခံလုပ်ဆောင်ရန်များ

## (၁) လုံခြုံရေးအခြေခံ

**User အသစ်ထည့်ပါ**

    adduser sandar
    
**အသစ်ထည့်ထားသော User အား sudo အုပ်စုထဲသို့ ထည့်ပါ**

    usermod -aG sudo sandar

**root အောက်မှ SSH Key အား အသစ်ထည့်ထားသော User အောက်သို့ ကူးထည့်ပါ**

    rsync --archive --chown=sandar:sandar ~/.ssh /home/sandar

**sshd_config ဖိုင်အား nano ဖြင့် ဖွင့်ပီး
PermitRootLogin no
ဟုပြင်ပါ**

    nano -w /etc/ssh/sshd_config

**SSH Service အား Restart လုပ်ပါ**

    service ssh restart

**PuTTY အား ပိတ်ပီး User အသစ်အကောင့်ဖြင့် ပြန်ဝင်ပါ**

## (၂) Server Update

**Server Update လုပ်ပါ**

    sudo apt update
    sudo apt upgrade -y
    sudo apt dist-upgrade -y

**Server Update လုပ်ပြီးလျှင် Reboot လုပ်ပါ**

    sudo reboot

## (၃) Time Zone

**Server Time Zone အား ပြင်ပါ**

    sudo dpkg-reconfigure tzdata

**NTP သွင်းပါ**

    sudo apt install ntp -y

## (၄) Autoremove

**Autoremove Setup လုပ်ပါ**

    sudo apt autoremove -y
    sudo sh -c 'echo "sudo apt autoremove -y" >> /etc/cron.monthly/autoremove'
    sudo chmod +x /etc/cron.monthly/autoremove
