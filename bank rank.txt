import random
from tkinter import *
import tkinter.messagebox
import time
import threading
import winsound
global x
global digs
global reum
global lonk
global ranc
global pond
global site
global exot
global inst
global mrkt
global m2
global b2
global c2
global a2
global j2
global h2
global n
global ne
global s2
s = 1
s2 = 10
m = 5
m2 = 48
b = 9
b2 = 63
c = 14
c2 = 47
a = 20
a2 = 44
j = 50
j2 = 9500
h = 150
h2 = 38333
x = 0
inst = 0
n = 32
exot = 0
digs = 0
ne = 300
mrkt = 0
lonk = 1
ranc = 0
pond = 0
site = 0
reum = 0
def bonusplus():
    global digs
    global reum
    global lonk
    global ranc
    global pond
    global site
    global exot
    global inst
    global mrkt
    for x in range(0, lonk):
        reum = reum + random.randint(0, s)
    for x in range(0, digs):
        reum = reum + random.randint(4, m)
    for x in range(0, ranc):
        reum = reum + random.randint(6, b)
    for x in range(0, pond):
        reum = reum + random.randint(2, c)
    for x in range(0, site):
        reum = reum + random.randint(4, a)
    for x in range(0, inst):
        reum = reum + random.randint(8, j)
    for x in range(0, mrkt):
        reum = reum + random.randint(16, h)

def augustus():
    lab = Label(utheroot, text="YOU ARE THE WEALTHIEST PERSON IN HISTORY***" )
    lab.grid(row=1, column=15)
    lob = Label(utheroot, text="as rich as augustus ceasar")
    lob.grid(row=2, column=15)
    und = Label(utheroot, text="***this cant be proven since wealth is difficult to measure with all of the leaders of nations")
    und.grid(row=6, column=15)





def clickz():
    global x
    if x == 0:
        def f(f_stop):
            bonusplus()
            _reumamount.config(text=reum)
            if reum > 4900000:
                augustus()
            if s > 20:
                s2 = s2 + 5
            if m > 25:
                m2 = m2 + 5
            if b > 30:
                b2 = b2 + 1
            if c > 35:
                c2 = c2+ 1
            if not f_stop.is_set():
                threading.Timer(2, f, [f_stop]).start()

        f_stop = threading.Event()
        # start calling f now and every 60 sec thereafter
        f(f_stop)
        x = 1


def lonkshack():
    time.sleep(.15)
    global reum
    global lonk
    global n
    if reum > n:
        lonk = lonk + 1
        _lonkamount.config(text=lonk)
        reum = reum - (n + 1)
        _reumamount.config(text=reum)
        winsound.PlaySound("ka-ching_sound_effect-vBYJdZlpBT4.wav", winsound.SND_ASYNC)
        n = n + 1
        scost.config(text=n)
        if n > 150:
            tkinter.messagebox.showinfo('ingame message', "monopoly charges you will get a tax")
            n = n + 50
            scost.config(text=n)

    else:
        tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")

def lonkacqu():
    global reum
    global s
    global s2
    if reum > s2:
        s = s + 1
        sspeed.config(text=s)
        _lonkamount.config(text=lonk)
        reum = reum - (s2 + 1)
        _reumamount.config(text=reum)
        s2 = s2 + 3


    else:
        tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")

def digsshack():
    time.sleep(.15)
    global digs
    global ne
    global reum
    if reum > ne:
        digs = digs + 1
        _digsamount.config(text=digs)
        reum = reum - (ne + 1)
        _reumamount.config(text=reum)
        winsound.PlaySound("ka-ching_sound_effect-vBYJdZlpBT4.wav", winsound.SND_ASYNC)
        if ne > 450:
            tkinter.messagebox.showinfo('ingame message', "monopoly charges you will get a small tax")
            ne = ne + 25
            scost.config(text=ne)

    else:
        tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")


def digsacqu():
    global m2
    global m
    global reum
    if reum > m2:
        m = m + 1
        mspeed.config(text=m)
        _digsamount.config(text=digs)
        reum = reum - (m2 + 1)
        _reumamount.config(text=reum)
        m2 = m2 + 3

    else:
        tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")

def rancshack():
    time.sleep(.25)
    global ranc
    global reum
    if reum > 904:
        ranc = ranc + 1
        _rancamount.config(text=ranc)
        reum = reum - 905
        _reumamount.config(text=reum)
        winsound.PlaySound("ka-ching_sound_effect-vBYJdZlpBT4.wav", winsound.SND_ASYNC)

    else:
        tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")

def rancacqu():
    global b2
    global b
    global reum
    if reum > b2:
        b = b + 1
        bspeed.config(text=b)
        _rancamount.config(text=ranc)
        reum = reum - (b2 + 1)
        _reumamount.config(text=reum)
        b2 = b2 + 4

    else:
        tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")

def pondshack():
    time.sleep(.25)
    global pond
    global reum
    global exot
    if reum > 2500:
        if exot == 0:
            pond = pond + 1
            _pondamount.config(text=pond)
            reum = reum - 2501
            _reumamount.config(text=reum)
            winsound.PlaySound("ka-ching_sound_effect-vBYJdZlpBT4.wav", winsound.SND_ASYNC)

        else:
            tkinter.messagebox.showinfo('ingame message',
                                        "sorry you dont have enough of something to get that now")
    else:
        tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")
def pondacqu():
    global c2
    global c
    global reum
    if reum > c2:
        if exot == 0:
            c = c + 1
            cspeed.config(text=c)
            _pondamount.config(text=pond)
            reum = reum - (c2 + 1)
            _reumamount.config(text=reum)
            c2 = c2 + 5

        else:
            tkinter.messagebox.showinfo('ingame message',
                                        "sorry you dont have enough of something to get that now")
    else:
        tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")


def siteshack():
    time.sleep(.5)
    global site
    global reum
    global exot
    if reum > 12000:
        if exot == 0:
            if pond > 1:
                site = site + 1
                _siteamount.config(text=site)
                reum = reum - 12001
                _reumamount.config(text=reum)
                winsound.PlaySound("america.wav", winsound.SND_ASYNC)
            else:
                tkinter.messagebox.showinfo('ingame message',
                                            "sorry you dont have enough of something to get that now")
    else:
        tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")
def siteacqu():
    global a2
    global a
    global reum
    if reum > a2:
        if exot == 0:
            if exot == 0:
                time.sleep(.75)
                a = a + 1
                aspeed.config(text=a)
                _siteamount.config(text=site)
                reum = reum - (a2 + 1)
                _reumamount.config(text=reum)
                a2 = a2 + 7

            else:
                tkinter.messagebox.showinfo('ingame message',
                                            "sorry you dont have enough of something to get that now")
    else:
        tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")
    time.sleep(.25)

def instshack():
    global inst
    global reum
    if reum > 155000:
        if exot == 0:
            if exot == 0:
                inst = inst + 1
                _instamount.config(text=inst)
                reum = reum - 155001
                _reumamount.config(text=reum)
                winsound.PlaySound("ofortuna.wav", winsound.SND_ASYNC)
        else:
            tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")
    else:
        tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")
def instacqu():
    global j2
    global j
    global reum
    if reum > j2:
        if exot == 0:
            if exot == 0:
                j = j + 2
                jspeed.config(text=j)
                _instamount.config(text=inst)
                reum = reum - (j2 + 1)
                _reumamount.config(text=reum)
                j2 = j2 + 3
        else:
            tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")
    else:
        tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")


def mrktshack():
    global mrkt
    global reum
    if reum > 350000:
        if exot == 0:
            if exot == 0:
                mrkt = mrkt + 1
                _mrktamount.config(text=mrkt)
                reum = reum - 350001
                _reumamount.config(text=reum)
                winsound.PlaySound("como.wav", winsound.SND_ASYNC)
        else:
            tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")
    else:
        tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")

def mrktacqu():
    global h2
    global h
    global reum
    if reum > h2:
        if exot == 0:
            if exot == 0:
                h = h + 3
                hspeed.config(text=h)
                _mrktamount.config(text=mrkt)
                reum = reum - (h2 + 1)
                _reumamount.config(text=reum)
                h2 = h2 + 2
        else:
            tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")
    else:
        tkinter.messagebox.showinfo('ingame message', "sorry you dont have enough of something to get that now")

utheroot = Tk()
utheroot.title("bank rank")
chinas = PhotoImage(file="ICBC.png")
morgan = PhotoImage(file="Chase-Bank-Logo.png")
americ = PhotoImage(file="colored_flagscape.png")
centra = PhotoImage(file="RBI.png")
bigban = PhotoImage(file="PNC.png")
medban = PhotoImage(file="nd2.png")
smaban = PhotoImage(file="FS.png")

clicko = Button(utheroot, text='start game', command=clickz)
clicko.grid(row=0, column=3)

r_my = Label(utheroot, text='MY')
r_my.grid(row=2, column=0, sticky=W)

r_wallet = Label(utheroot, text='MONEY')
r_wallet.grid(row=3, column=0, sticky=W)

_reumamount = Label(utheroot, text=reum)
_reumamount.grid(row=4, column=0, sticky=E)

r_wallet = Label(utheroot, text='million')
r_wallet.grid(row=4, column=1, sticky=W)

# number 1 is empty #

m_title = Label(utheroot, text='BANK RANK')
m_title.grid(row=0, column=2)

m_lonk = Label(utheroot, text='small bank')
m_lonk.grid(row=2, column=3)

lsmaban = Label(utheroot, image=smaban)
lsmaban.grid(row=1, column=3)

_lonkamount = Label(utheroot, text=lonk)
_lonkamount.grid(row=3, column=3)

lonkadd = Button(utheroot, text='buy small bank', command=lonkshack)
lonkadd.grid(row=4, column=3)

lonkadd2 = Button(utheroot, text='add profit speed', command=lonkacqu)
lonkadd2.grid(row=5, column=3)

sspeed = Label(utheroot, text=s, fg="green")
sspeed.grid(row=6, column=3)
scost = Label(utheroot, text=n, fg="gray")
scost.grid(row=7, column=3)
m_digs = Label(utheroot, text='medium bank')
m_digs.grid(row=2, column=6)

_digsamount = Label(utheroot, text=digs)
_digsamount.grid(row=3, column=6)

lmedban = Label(utheroot, image=medban)
lmedban.grid(row=1, column=6)

digsadd = Button(utheroot, text='buy medium bank', command=digsshack)
digsadd.grid(row=4, column=6)

digsadd2 = Button(utheroot, text='add profit speed', command=digsacqu)
digsadd2.grid(row=5, column=6)
mspeed = Label(utheroot, text=m, fg="green")
mspeed.grid(row=6, column=6)
mcost = Label(utheroot, text=ne, fg="gray")
mcost.grid(row=7, column=6)
m_ranc = Label(utheroot, text='big bank')
m_ranc.grid(row=2, column=9)

_rancamount = Label(utheroot, text=ranc)
_rancamount.grid(row=3, column=9)

lbigban = Label(utheroot, image=bigban)
lbigban.grid(row=1, column=9)

rancadd = Button(utheroot, text='buy big bank', command=rancshack)
rancadd.grid(row=4, column=9)

rancadd2 = Button(utheroot, text='add profit speed', command=rancacqu)
rancadd2.grid(row=5, column=9)
bspeed = Label(utheroot, text=b, fg="green")
bspeed.grid(row=6, column=9)
bcost = Label(utheroot, text="905", fg="gray")
bcost.grid(row=7, column=9)
m_pond = Label(utheroot, text='central bank')
m_pond.grid(row=2, column=12)

_pondamount = Label(utheroot, text=pond)
_pondamount.grid(row=3, column=12)

lcentra = Label(utheroot, image=centra)
lcentra.grid(row=1, column=12)

pondadd = Button(utheroot, text='buy central bank', command=pondshack)
pondadd.grid(row=4, column=12)

pondadd2 = Button(utheroot, text='add profit speed', command=pondacqu)
pondadd2.grid(row=5, column=12)
cspeed = Label(utheroot, text=c, fg="green")
cspeed.grid(row=6, column=12)
ccost = Label(utheroot, text="2500", fg="gray")
ccost.grid(row=7, column=12)
m_site = Label(utheroot, text='american bank', fg="purple")
m_site.grid(row=10, column=3)

_siteamount = Label(utheroot, text=site)
_siteamount.grid(row=11, column=3)

lameric = Label(utheroot, image=americ)
lameric.grid(row=9, column=3)

siteadd = Button(utheroot, text='buy american bank', command=siteshack)
siteadd.grid(row=12, column=3)

siteadd2 = Button(utheroot, text='add profit speed', command=siteacqu)
siteadd2.grid(row=13, column=3)
aspeed = Label(utheroot, text=a, fg="green")
aspeed.grid(row=14, column=3)
acost = Label(utheroot, text="12000", fg="gray")
acost.grid(row=15, column=3)
m_inst = Label(utheroot, text='morgan banks', fg="purple")
m_inst.grid(row=10, column=6)

_instamount = Label(utheroot, text=inst)
_instamount.grid(row=11, column=6)
lmorgan = Label(utheroot, image=morgan)
lmorgan.grid(row=9, column=6)
instadd = Button(utheroot, text='buy morgan bank', command=instshack)
instadd.grid(row=12, column=6)

instadd2 = Button(utheroot, text='add profit speed', command=instacqu)
instadd2.grid(row=13, column=6)
jspeed = Label(utheroot, text=j, fg="green")
jspeed.grid(row=14, column=6)
jcost = Label(utheroot, text="155000", fg="gray")
jcost.grid(row=15, column=6)
m_mrkt = Label(utheroot, text='chinese bank', fg="purple")
m_mrkt.grid(row=10, column=9)

_mrktamount = Label(utheroot, text=mrkt)
_mrktamount.grid(row=11, column=9)

lchinas = Label(utheroot, image=chinas)
lchinas.grid(row=9, column=9)

mrktadd = Button(utheroot, text='buy chinese bank', command=mrktshack)
mrktadd.grid(row=12, column=9)

mrktadd2 = Button(utheroot, text='add profit speed', command=mrktacqu)
mrktadd2.grid(row=13, column=9)

hspeed = Label(utheroot, text=h, fg="green")
hspeed.grid(row=14, column=9)
hcost = Label(utheroot, text="350000", fg="gray")
hcost.grid(row=15, column=9)
uspeed = Label(utheroot, text="green digits are MAX profit per 2 seconds", fg="green")
uspeed.grid(row=9, column=12)
ubspeed = Label(utheroot, text="gray digits are price of banks", fg="gray")
ubspeed.grid(row=10, column=12)
utheroot.mainloop()