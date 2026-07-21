import random

words = ["apple","grapes","orange","jackfruit","cherry","lichi","pineapple"]

hangman_art= {0:("   ", "   ","   "),
1:(" O  ",
   "    ",
   "    "),
2:(" O  ",
   " |  ",
   "    "),
3:(" O  "
,  "/|   ",
   "   "),
4:(" O  ",
  " /|\\   "
  ,"   "),
5:(" O  ",
  " /|\\   ",
  " /  "),
6:(" O  ",
   "/|\\    ",
   "/ \\    ")}

def display_man(wrong_ans):
   print("**********")
   for line in hangman_art[wrong_ans]:
      print(line)
      print("**********")


def display_hint(hint):
   print( " ".join(hint))

def display_ans(ans):
   print( " ".join(ans))

def main():
    ans = random.choice(words)
    hint= ["_"]*len(ans)
    wrong_ans = 0
    guess_letter= set()
    is_running= True
    print('guess a fruit name')

    while is_running:
       display_man(wrong_ans)
       display_hint(hint)

       guess= input("enter a letter: ").lower()

       if len(guess)!=1 or not guess.isalpha():
          print("invalid input")
          continue
       if guess in guess_letter:
          print(f"{guess} is already guessed")
          continue
       guess_letter.add(guess)

       if guess in ans:
          for i in range(len(ans)):
             if ans[i]==guess:
                hint[i]=guess

       else:
          wrong_ans+=1
       if "_" not in hint:
           display_man(wrong_ans)
           display_ans(ans)
           print("u win")
           is_running = False

       elif wrong_ans>=len(hangman_art) -1:
           display_man(wrong_ans)
           display_ans(ans)
           print("u lose")
           is_running=False


if __name__=="__main__":
  main()
