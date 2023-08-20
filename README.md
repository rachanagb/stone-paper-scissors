# stone-paper-scissors
#game

from tkinter import*
import random
root=Tk()
root.geometry('200x200')
root.title('ROCK PAPER SCISSOR')
compval={'0':'ROCK','1':'PAPER','2':'SCISSOR'}
points1 =0
points2 =0
points3=0
points4=0
def points(result):
   global points1
   global points2
   if result == 'YAAAYYYY!!! YOU WON :)':
        canvas_scoreboard1.delete('all')
        points1+=1
   elif result =='YOU LOST:(':
        canvas_scoreboard2.delete('all')
        points2+=1
   canvas_scoreboard1.create_text(20,20,text=points1,fill='black')

   canvas_scoreboard2.create_text(20,20,text=points2,fill='black')

   if points2>=5:
          window2.quit()


   if points1>=5:
    compval1 = {'0':'ROCK','1':'PAPER','2':'SCISSOR','3':'LIZARD','4':'SPOCK'}


    def points_2(result1):
        global points3
        global points4
        global canvas_scoreboard3
        global canvas_scoreboard4
        if result1 == 'YAAAYYYY!!! YOU WON :)':
            canvas_scoreboard3.delete('all')
            points3+=1
        elif result1 =='YOU LOST :(':
            canvas_scoreboard4.delete('all')
            points4+=1
        canvas_scoreboard3.create_text(20,20,text=points3,fill='black')

        canvas_scoreboard4.create_text(20,20,text=points4,fill='black')
    

    def spock():
        computer1 = compval1[str(random.randint(0,4))]
        if computer1=='SPOCK':
            result1 = 'DRAW MATCH'
        elif computer1 =='ROCK':
            result1= 'YAAAYYYY!!! YOU WON :)'
        elif computer1 == 'PAPER':
            result1 = 'YOU LOST :('
        elif computer1 =='SCISSOR':
            result1 = 'YAAAYYYY!!! YOU WON :)'
        else:
            result1 = 'YOU LOST :('
        Player1.config(text="SPOCK")
        Computer1.config(text=computer1)
        Display1.config(text=result1)
        points_2(result1)
    def lizard():
        computer1 = compval1[str(random.randint(0,4))]
        if computer1=='LIZARD':
            result1 ='DRAW MATCH'
        elif computer1=='ROCK':
            result1 = 'YOU LOST :('
        elif computer1 == 'PAPER':
            result1 = 'YAAAYYYY!!! YOU WON :)'
        elif computer1 == 'SPOCK':
            result1 = 'YAAAYYYY!!! YOU WON :)'
        else:
            result1= 'YOU LOST :('
        Player1.config(text ="LIZARD")
        Computer1.config(text=computer1)
        Display1.config(text=result1)
        points_2(result1)

    def isrock():
        computer1 = compval1[str(random.randint(0,4))]
        if computer1=='ROCK':
            result1 ='DRAW MATCH'
        elif computer1=='SPOCK':
            result1 = 'YOU LOST :('
        elif computer1 == 'LIZARD':
            result1 = 'YAAAYYYY!!! YOU WON :)'
        elif computer1 == 'SCISSOR':
            result1 = 'YAAAYYYY!!! YOU WON :)'
        else:
            result1= 'YOU LOST :('
        Player1.config(text='ROCK')
        Computer1.config(text=computer1)
        Display1.config(text=result1)
        points_2(result1)

    def ispaper():
        computer1 = compval1[str(random.randint(0,4))]
        if computer1=='PAPER':
            result1 ='DRAW MATCH'
        elif computer1=='SCISSOR':
            result1 = 'YOU LOST :('
        elif computer1 == 'ROCK':
            result1 = 'YAAAYYYY!!! YOU WON :)'
        elif computer1 == 'SPOCK':
            result1 = 'YAAAYYYY!!! YOU WON :)'
        else:
            result1= 'YOU LOST :('
        Player1.config(text='PAPER')
        Computer1.config(text=computer1)
        Display1.config(text=result1)
        points_2(result1)

    def isscissor():
        computer1 = compval1[str(random.randint(0,4))]
        if computer1=='SCISSOR':
            result1 ='DRAW MATCH'
        elif computer1=='ROCK':
            result1 = 'YOU LOST :('
        elif computer1 == 'PAPER':
            result1 = 'YAAAYYYY!!! YOU WON :)'
        elif computer1 == 'LIZARD':
            result1 = 'YAAAYYYY!!! YOU WON :)'
        else:
            result1= 'YOU LOST :('
        Player1.config(text='SCISSOR')
        Computer1.config(text=computer1)
        Display1.config(text=result1)
        points_2(result1)
    global window3   
    global Player1
    global Computer1
    global Display1
    global canvas_scoreboard3
    global canvas_scoreboard4
    window3=Toplevel(root)
    window3.title('ROCK PAPER SCISSOR LIZARD SPOCK')
    window3.geometry('270x400')
    button8=Button(window3,text='ROCK',fg='black',bg='white',command=isrock)
    button8.place(x=100,y=20)
    button9=Button(window3,text='PAPER',fg='black',bg='white',command=ispaper)
    button9.place(x=100,y=60)
    button10=Button(window3,text='SCISSOR',fg='black',bg='white',command=isscissor)
    button10.place(x=95,y=100)
    button11=Button(window3,text='LIZARD',fg='black',bg='white',command=lizard)
    button11.place(x=97,y=140)
    button12=Button(window3,text='SPOCK',fg='black',bg='white',command=spock)
    button12.place(x=100,y=180)
    button13=Button(window3, text='EXIT',fg='black',bg='white',command=window3.quit)
    button13.place(x=110,y=340)
    canvas_scoreboard3 = Canvas(window3,bg='white')
    canvas_scoreboard3.place(x=20,y=300,width=30,height=30)
    canvas_scoreboard4= Canvas(window3,bg='white')
    canvas_scoreboard4.place(x=200,y=300,width=30,height=30)
    labelscore1 = Label(window3,text='SCOREBOARD')
    labelscore1.place(x=87,y=300)
    Display1 = Label(window3,text="RESULT")
    Player1 = Label(window3,text='Player       ')
    Vs1 = Label(window3,text='VS      ')
    Computer1 = Label(window3,text='Computer')
    Player1.place(x=30,y=260)
    Vs1.place(x=110,y=260)
    Computer1.place(x=160,y=260)
    Display1.place(x=100,y=220)
    window3['background']='#6E6E8B'
    
    
def rock():
    computer=compval[str(random.randint(0,2))]
    if computer=='ROCK':
        result='DRAW MATCH'
    elif computer=='PAPER':
        result='YOU LOST:('
    else:
        result='YAAAYYYY!!! YOU WON :)'
    Player.config(text="ROCK    ")
    Computer.config(text=computer)
    Display.config(text=result)
    points(result)
    
def paper():
    computer=compval[str(random.randint(0,2))]
    if computer=='PAPER':
        result='DRAW MATCH'
    elif computer=='SCISSOR':
        result='YOU LOST:('
        
    else:
        result='YAAAYYYY!!! YOU WON :)'
    Player.config(text='PAPER   ')
    Computer.config(text=computer)
    Display.config(text=result)
    points(result)

def scissor():
    computer=compval[str(random.randint(0,2))]
    if computer=='SCISSOR':
        result='DRAW MATCH'
    elif computer=='ROCK':
        result='YOU LOST:('
       
    else:
        result='YAAAYYYY!!! YOU WON :)'
    Player.config(text='SCISSOR ')
    Computer.config(text=computer)
    Display.config(text=result)
    points(result)

def game():
    global Player
    global Computer
    global Display
    global canvas_scoreboard1
    global canvas_scoreboard2
    global window2
    window2=Toplevel(root)
    window2.title('ROCK PAPER SCISSOR')
    window2.geometry('250x300')
    button5=Button(window2,text='ROCK',fg='black',bg='white',command=rock)
    button5.place(x=100,y=20)
    button6=Button(window2,text='PAPER',fg='black',bg='white',command=paper)
    button6.place(x=100,y=60)
    button7=Button(window2,text='SCISSOR',fg='black',bg='white',command=scissor)
    button7.place(x=95,y=100)
    canvas_scoreboard1 = Canvas(window2,bg='white')
    canvas_scoreboard1.place(x=20,y=250,width=30,height=30)
    canvas_scoreboard2= Canvas(window2,bg='white')
    canvas_scoreboard2.place(x=200,y=250,width=30,height=30)
    labelscore = Label(window2,text='SCOREBOARD')
    labelscore.place(x=85,y=250)
    Display = Label(window2,text="result ")
    Player = Label(window2,text='Player       ')
    Vs = Label(window2,text='VS      ')
    Computer = Label(window2,text='Computer')
    Player.place(x=70,y=150)
    Vs.place(x=130,y=150)
    Computer.place(x=160,y=150)
    Display.place(x=50,y=190)
    window2['background']='#7979CD'

def start():
    global newwindow
    newwindow=Toplevel(root)
    newwindow.title('INSTRUCTIONS')
    newwindow.geometry('600x300')
    Label(newwindow,text='LEVEL-1').pack()
    Label(newwindow,text='A classic two-person game. Players start each round by saying, “rock, paper, scissors!".\n Rock crushes scissors, scissors cut paper, and paper covers rock. See who wins each round!\n').pack()
    Label(newwindow,text="THE GAME WILL AUTOMATICALLY CLOSE IF THE COMPUTER REACHES 5 POINTS FIRST",font='bold').pack()
    Label(newwindow,text='LEVEL-2').pack()
    Label(newwindow,text='Scissors cuts paper, paper covers rock, rock crushes lizard,\n lizard poisons Spock, Spock smashes scissors, scissors decapitates lizard,\n lizard eats paper, paper disproves Spock, Spock vaporizes rock, \n and as it always has, rock crushes scissors!').pack()
    button3=Button(newwindow,text='PLAY',fg='black',bg='white',command=game).pack()
    button4=Button(newwindow,text='EXIT',fg='black',bg='white',command=newwindow.quit).pack()
    newwindow['background']='#BCBCEE'
button1=Button(root,text='START',fg='black',bg='white',font ="bold",command=start).pack()
button2=Button(root,text='EXIT',fg='black',bg='white',command=root.quit).pack()
root['background']='#CACAFF'
root.mainloop()




