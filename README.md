# Simple-slotmachine-game
A python written game that uses the output to control the game. Feel free to copyNpaste or modify it as you wish!
Copy the code below or download the .py file attached:

#code start
import random
lucky_numbs =[45, 46, 47, 48, 49, 51, 52, 53, 54, 55]

truue = True

def menu():
  money = 0
  my_money = 0
  chance = 10
  sus = 1
  while truue == True:

    choice = int(input("What do you want to do?\n1: play one time\n2: go to shop\n3: withdraw money\n4: check your stats\n11: play multiple times\n"))

    if choice == 1:
      sus = 1
      price = random.randint(sus, 150)
      x = random.randint(0, 100)
      if x in lucky_numbs:
        print(f"Yay, you've just won ${price}!")
        money += price
      else:
        print("Sorry, no price for you this time...better luck next time!")
    elif choice == 11:
      kaka = int(input(f"How many times do you want to play?  \n"))
      for i in range(kaka):
        sus = 1
        price = random.randint(sus, 150)
        x = random.randint(0, 100)
        if x in lucky_numbs:
          print(f"Yay, you've just won ${price}!")
          money = money + price
        else:
          print("Sorry, no price for you this time...better luck next time!")
    elif choice == 2:
      print("Welcome to the shop! Buy every upgrade you want unless you have no money!")
      print(f"\nItems:\n+1% chance to win: $5\n+10$ max price: $10\n\n")
      buy = input("What do you want to buy? Enter 1 and 2 to buy or 3 to exit:   ")
      if buy == 1 and my_money > 5:
        fuui = random.randint(0, 100)
        if fuui not in lucky_numbs:
          lucky_numbs.append(fuui)
          print("Item successfully purchased!\n")
          my_money -= 5
          chance += 1
        else:
          print(f"Oops, something went wrong, try again later..")
      elif buy == 1 and my_money < 5:
        print(f"You don't have enough money on your account! Current balance:\n {my_money}\n")
      elif buy == 2 and my_money > 10:
        sus = 10
        print(f"Item successfully purchased!\n")
      elif buy == 2 and my_money < 10:
        print(f"You don't have enough money on your account! Current balance:\n {my_money}\n")
      elif buy == 3:
        print(f"Exiting the shop..done")

    elif choice == 3:
      print(f"Your withdrawable money: {money}\nYour bank account: {my_money}\n")
      w_choice = input(f"Do you want to withdraw ${money} to your bank account? y/n:\n")
      if w_choice == "y":
        my_money += money
        money = 0
        print(f"Successfully withdrawed the money!")
      elif w_choice == "n":
        print(f"Withdrawal canceled..")
      else:
        print(f"Input not reconized...try again..")
        return
    elif choice == 4:
      print(f"Machines money/withdrawable money: ${money}\nYour money on your bank account: ${my_money}\nYour Current chance for a jackpot: {chance}%\nSmallest price at a jackpot: ${sus}\n")
    else:
      print(f"Not an valid input..")
menu()
