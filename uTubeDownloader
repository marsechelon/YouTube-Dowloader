#!/user/bin/python2.7
# -*-coding:Utf-8 *-

import Tkinter
from Tkinter import *
from tkMessageBox import *
import os

class Downloader(Tkinter.Tk):

    def __init__(self):
        Tkinter.Tk.__init__(self)

        # Create the Canvas
        
        self.App = Tkinter.Canvas(self , width = 50 , height = 50 ,bg = 'white')
        self.App.pack()
        # Choose type of conversion !!!
        
        self.DownloadButton = Tkinter.Button(self , text = 'Download Video From YouTube' , command = self.DownloadVideo)
        self.DownloadButton.pack()
        self.AudioButton = Tkinter.Button(self , text = 'Extract-Audio From A YouTube Video' , command = self.DownloadAudio)
        self.AudioButton.pack()

        # Create a Menu
        self.menuBar = Menu(self)
        self.ppe_menu = Menu(self.menuBar , tearoff = 0)
        self.ppe_menu.add_command(label = "About" , command = self.aboutMenu)
        self.ppe_menu.add_separator()
        self.menuBar.add_cascade(label = "About" , menu = self.ppe_menu)
        self.config(menu = self.menuBar)

    def DownloadVideo(self):
        # Creer le champs d'url
        # Create the Canvas
        self.DownVid = Tkinter.Canvas(self , width = 50 , height = 50 ,bg = 'white')
        self.DownVid.pack()

        self.DownVid.url = Tkinter.StringVar()
        self.DownVid.url.set("Url....")
        self.DownVid.urlEntry = Tkinter.Entry(self ,textvariable = self.DownVid.url , width = 30 )
        self.DownVid.urlEntry.pack(side = TOP)
        self.DownVid.format = Tkinter.StringVar()
        self.DownVid.format.set("Format")
        self.DownVid.formatEntry = Tkinter.Entry(self ,textvariable = self.DownVid.format , width = 7 )
        self.DownVid.formatEntry.pack()
        #Create Download Button
        self.DownVid.dlbt = Tkinter.Button(self  , text = 'Download' , command = self.dlVideo)
        self.DownVid.dlbt.pack()

    def aboutMenu(self):

        showinfo("About" , "Ahadri Hatim , Follow me on Twitter @hatimahadri")



    def dlVideo(self):
        os.system("youtube-dl -citk  --list-formats -f "+str(self.DownVid.format.get())+" "+str(self.DownVid.url.get())+" > info.txt")
        os.system("youtube-dl -citk  -f "+str(self.DownVid.format.get())+" "+str(self.DownVid.url.get())+" > info.txt")

        self.DownVid.label = Label(self, text = "For more details check the info file !!" , bg = "yellow")
        self.DownVid.label.pack()


    def DownloadAudio(self):

        # Create the Canvas
        self.DownAud = Tkinter.Canvas(self , width = 50 , height = 50 ,bg = 'white')
        self.DownAud.pack()

        # Creer le champs d'url
        self.DownAud.url = Tkinter.StringVar()
        self.DownAud.url.set("Url....")
        self.DownAud.urlEntry = Tkinter.Entry(self ,textvariable = self.DownAud.url , width = 30 )
        self.DownAud.urlEntry.pack()

        #Create Download Button
        self.DownAud.dlbt = Tkinter.Button(self  , text = 'Download' , command = self.dlAudio)
        self.DownAud.dlbt.pack()
        #self.DownAud.mainloop()


    def dlAudio(self):
        os.system("youtube-dl --extract-audio --audio-format mp3 --output \"%(uploader)s%(title)s.%(ext)s\" "+str(self.DownAud.url.get()))



if __name__ == '__main__':
    Application = Downloader()
    Application.mainloop()
