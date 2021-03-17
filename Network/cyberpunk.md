it's a chall regarding the tcp streams
so we need to extract the data from the 3 tcp stream's "5,7,8" so as i discussed about scapy i used that to extract
```from scapy.all import *
f=rdpcap('./Downloads/CY.pcap')
b=''
for i in f[TCP]:
	if ":54166" in i.summary() and len(i)>214:
		b+=bytes(i).hex()[132:]
data = bytes.fromhex(b)
open("a.png", 'wb').write(data)
```
```from scapy.all import *
f=rdpcap('./Downloads/CY.pcap')
b=''
for i in f:
	if ":60192" in i.summary()  and  len(i)>214:
		b+=bytes(i).hex()[132:]

da = bytes.fromhex(b)
open("ab.png", 'wb').write(da)
```
```from scapy.all import *
f=rdpcap('./Downloads/CY.pcap')
b=''
for i in f[TCP]:
	if ":45098" in i.summary() and  len(i)>214:
		b+=bytes(i).hex()[132:]
print(b)
da = bytes.fromhex(b)
open("p3.png", 'wb').write(da)
```
i got 3 images and we need to overlay those to get the required flag. so i used "PIL" which helped me to do that

```from PIL import Image
im1 = Image.open("p1.png")
im2 = Image.open("p2.png")
blended = Image.blend(im1, im2, alpha=0.5)
blended.save("blended.png")```


