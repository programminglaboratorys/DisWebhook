# DisWebhook
a easy tool for discord webhooks
# installation

Run the following to install:
```cmd
pip install DisWebhook
```
### or
```cmd
python -m pip install DisWebhook
```
if that didn't work, try replacing `pip` with `pip3`.
need help? my discord: [lab](https://discord.gg/vzEZnC7CM8)


# useg
## simple example
```py
from DisWebhook import DisWebhook
import time

mywebhook = DisWebhook(url)
print(mywebhook)
print("sending a \"Hello, World!\" Message")
msg = mywebhook.send("Hello, World!")
time.sleep(2)
msg = msg.edit("Hello User, are you seeing this?")
print(msg)
time.sleep(4)
print("editing the Message")
msg.edit("Hello User, i am going to delete this hehe :)")
time.sleep(2)
print("deleting the Message")
msg.delete()
```
## edit
```py
from DisWebhook import Message

url = "url"
# editing an existing message
mymsg = Message(url)
msg = mymsg.edit("Hello, World!")
print(mymsg)
print(msg)
```
![massega_send_edit_delete](https://raw.githubusercontent.com/programminglaboratorys/DisWebhook/main/DisWebhook/IMGS/massage_send_edit_dellete.gif)
## Embeds
```py
from DisWebhook import DisWebhook
from DisWebhook import Embed
import time

mywebhook = DisWebhook(url)
# works like discord.py embed
embed = Embed(title="embed title",description="Hello i am an embed")

print(dir(embed)) # look at the attrs

embed.add_field(name="Field1", value="hi", inline=False)
embed.add_field(name="Field2", value="hi2", inline=False)

mywebhook.send(embed=embed)
```
![embeds](https://raw.githubusercontent.com/programminglaboratorys/DisWebhook/main/DisWebhook/IMGS/embeds.png)
# Files
```py
from DisWebhook import DisWebhook
from DisWebhook import File

mywebhook = DisWebhook(url)

myfile = File(name="green.png",path="D:\\Users\\Me\\Pictures\\color") # or File(name="file.png",content=open(file).read()) a wrapper on TextIOWrapper
myfile.read(mode="rb") # you must read the file or the content will be empty
myfile2 = File(name="green.txt",content="ayo whats up i am a text file") # a wrapper on StringIO object; no need to set/read the content
mywebhook.add_file(myfile) # add the file object make sure its the File object or you may get unexpected errors
mywebhook.add_file(myfile2)
mywebhook.send() # send the files
```
![files](https://raw.githubusercontent.com/programminglaboratorys/DisWebhook/main/DisWebhook/IMGS/files.png)
Change Log
==========

0.1.0 (2022/7/4)
-------------------
- First Release

