

## VestaCP နှင့် WordPress သွင်းနည်း

**(၁) VestaCP သွင်းရန်**

    sudo -i
    curl -O http://vestacp.com/pub/vst-install.sh
    bash vst-install.sh --force

**(၂) WordPress သွင်းရန်**
ပထမဦးစွာ VestaCP ထဲသို့ ဝင်ပြီး admin password ချိန်းပါ။ ထို့နောက် WEB အောက်မှ Default Domain ကို ဖျက်ပါ။ ပြီးလျှင် သက်ဆိုင်ရာ Domain ကို ထည့်ပြီး DNS Support ကို ဖြုတ်၍ Add လုပ်ပါ။ Domain ထည့်ပြီးလျှင် MAIL ထဲသို့ သွားပြီး admin mail အကောင့်အသစ်လုပ်ပါ။ ပြီးလျှင် PuTTY ထဲတွင် အောက်ပါ command များကိုရိုက်၍ WordPress သွင်းပါ။

    cd /home/admin/web/binaryland.biz/public_html
    rm -Rf *
    wget https://wordpress.org/latest.tar.gz
    tar -xzvf latest.tar.gz
    mv wordpress/* .
    rmdir wordpress && rm latest.tar.gz
    chown -R admin.admin *

WordPress သွင်းပြီးလျှင် VestaCP ထဲသို့ ဝင်၍ DB ထဲသို့ သွားပြီး Database အသစ်ဆောက်ခါ သက်ဆိုင်ရာ url ကို ဖွင့်ပြီး WordPress အား Setup ဆက်လုပ်ပါ။
