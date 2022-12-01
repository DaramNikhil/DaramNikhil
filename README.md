#simple caluculater
import tkinter as tk

from tkinter import *


tkn=tk.Tk()
tkn.title("simple caluculator")

def clear():
    cal.delete(0,END)    
def display(myth):
    ok=str(cal.get())
    clear()
    cal.insert(0,ok+str(myth))    
gs=''
ps=''
k1=0
def calc(cm,sign):
    global gs,ps,k1
    gs=cm
    ps=sign
    k1=int(cal.get())
    clear()
    cal.insert(0,str(k1)+ps)
    
def equal():
    global k1
    k2=cal.get().replace(str(k1)+ps,'')
    clear()
    if gs=='add':
        final=int(k1)+int(k2)
        cal.insert(0,final)
        
    elif gs=='sub':
        final=int(k1)-int(k2)
        cal.insert(0,final)
        
    elif gs=='mul':
        final=int(k1)*int(k2)
        cal.insert(0,final)
        
    elif gs=='div':
        final=int(k1)/int(k2)
        cal.insert(0,final)
        


    

cal=Entry(tkn,width=14,font=("arial",10),justify=RIGHT)
cal.grid(row=0,column=0,padx=5,pady=5,columnspan=3)
#buttons
buton_0=Button(tkn,text="0",padx=36,pady=10,font=("arial",14),command=lambda:display(0),relief=RAISED,bd=5)
buton_1=Button(tkn,text="1",padx=36,pady=10,font=("arial",14),command=lambda:display(1),relief=RAISED,bd=5)
buton_2=Button(tkn,text="2",padx=36,pady=10,font=("arial",14),command=lambda:display(2),relief=RAISED,bd=5)
buton_3=Button(tkn,text="3",padx=36,pady=10,font=("arial",14),command=lambda:display(3),relief=RAISED,bd=5)
buton_4=Button(tkn,text="4",padx=36,pady=10,font=("arial",14),command=lambda:display(4),relief=RAISED,bd=5)
buton_5=Button(tkn,text="5",padx=36,pady=10,font=("arial",14),command=lambda:display(5),relief=RAISED,bd=5)
buton_6=Button(tkn,text="6",padx=36,pady=10,font=("arial",14),command=lambda:display(6),relief=RAISED,bd=5)
buton_7=Button(tkn,text="7",padx=36,pady=10,font=("arial",14),command=lambda:display(7),relief=RAISED,bd=5)
buton_8=Button(tkn,text="8",padx=36,pady=10,font=("arial",14),command=lambda:display(8),relief=RAISED,bd=5)
buton_9=Button(tkn,text="9",padx=36,pady=10,font=("arial",14),command=lambda:display(9),relief=RAISED,bd=5)

#buton.clear
buton_clear=Button(tkn,text="clear",font=("arial",14),relief=RAISED,command=clear,bd=5)
#buton.div
buton_div=Button(tkn,text="/",font=("arial",14),padx=41,pady=10,relief=RAISED,command=lambda:calc('div','/'),bd=5)
#buton.mul
buton_mul=Button(tkn,text="*",font=("arial",14),padx=45,pady=10,relief=RAISED,command=lambda:calc('mul','*'),bd=5)
#buton.add
buton_addk=Button(tkn,text="+",font=("arial",14),padx=39,pady=10,relief=RAISED,command=lambda:calc('add','+'),bd=5)
#buton.sub
buton_sub=Button(tkn,text="-",font=("arial",14),padx=45,pady=10,relief=RAISED,command=lambda:calc('sub','-'),bd=5)
#buton.eql
buton_eql=Button(tkn,text="=",font=("arial",14),padx=45,pady=75,relief=RAISED,command=equal,bd=5)


buton_clear.grid(row=4,column=1,padx=5,pady=5,columnspan=2)
buton_div.grid(row=5,column=0,padx=2,pady=2)
buton_mul.grid(row=5,column=1,padx=2,pady=2)
buton_addk.grid(row=6,column=1,padx=2,pady=2)
buton_sub.grid(row=6,column=0,padx=2,pady=2)
buton_eql.grid(row=5,column=2,padx=2,pady=2,rowspan=2)



buton_7.grid(row=1 ,column= 0,padx=5,pady=2)
buton_8.grid(row=1 ,column= 1,padx=5,pady=2)
buton_9.grid(row=1 ,column= 2,padx=5,pady=2)

buton_6.grid(row=2 ,column=0 ,padx=2,pady=2)
buton_5.grid(row=2,column= 1,padx=2,pady=2)
buton_4.grid(row=2 ,column= 2,padx=2,pady=2)

buton_3.grid(row=3 ,column= 0,padx=2,pady=2)
buton_2.grid(row=3 ,column= 1,padx=2,pady=2)
buton_1.grid(row=3 ,column=2 ,padx=2,pady=2)

buton_0.grid(row=4 ,column=0 ,padx=2,pady=2)


mainloop()
