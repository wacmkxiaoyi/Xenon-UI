# Xenon-UI (XUI)

XUI is a page management GUI framework for python that is based on the platform-independent GUI package tinker.

# Install

Please enter the following code on the command line to install

```shell
pip3 install XUI
```

# Create a page

XUI is based on **page** management. The page is the basic unit of XUI, and here we will create a page "pageA" and place it into the folder **pages**.

And each page has many **menus**, and all information will be concentrated in each **menu**.

```python
#pageA
import os
from XUI.XUIlib.imgtool import add_image
from XUI.XUIlib.page import *
logo=os.path.join("XUI","XUIlib","image","A.png") #select a logo you like
from tkinter import *

class page(page):
	img={
		"logo":logo
	}
	def menu1(self):	
		self.menu1=self.add_menu("menu1") #set menu

    #add a title, can be call repeatedly
		self.add_title(self.menu1,"Title of Menu 1")
    #other arguments of add_title:
    #bg: color of title, default "blue"
		#fontsize: size of title, default 18
    #height: title height, default 50

    #add a row object
    row=self.add_row(self.menu1)
    #other arguments of add_row:
    #bx: boundary x, (like margin_left/right in HTML), default 50
    #height: height of row

    #dosomething like using the tinker, with father object row
    #e.g. a label
    Label(row,text="this is a label").pack(side="left")
    #an input box
    Entry(row).pack(side="left")
    #a button
    Button(row).pack(side="left")
    #.....

	def menu2(self):
    menu2=self.add_menu("menu2") #set menu2
    self.add_title(menu2,"Title of Menu 2")
    #do something as your wish
	def initial(self): # this function builds up this page
		self.set_image(self.img["logo"])
		self.menu1()
		self.menu2()
	def show(self): #Default page
    #This function means that as soon as you open XUI, the contents of this directory will be displayed
    #you have to define default menu with the attribute of <class page>, such as self.menu1
		self.tkobj.open_smb(None,self.fmbindex)
```
		self.tkobj.open_ro(None,self.fmbindex,self.menu1)
```
