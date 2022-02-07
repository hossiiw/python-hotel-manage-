from random import randint as rn


class Hotelmanage():
   
   def __init__(self,name = '' , sexual = '' , address = '' , cindate = '' , coutdate = '' , room_pay = 0 ,room_number = 1, empty_room = 99 , full_room = 1 , room_A = 40 , room_B = 30 , room_C = 20 , room_D = 10 , food_pay= 0 , Dessert = 70 , Drink = 200 , Breakfast = 100 , Lunch = 100 , Dinner = 100 , total_pay = 0 , guess_user_point = 0 , guess_bot_point = 0 , rps_user_score = 0 , rps_bot_score = 0):
   
      #information of person
      self.name = name
      self.sexual = sexual
      self.address = address
      self.cindate = cindate
      self.coutdate = coutdate

      #roomrent information
      self.room_pay = room_pay
      self.empty_room = empty_room
      self.full_room = full_room
      self.room_number = room_number
      self.room_A = room_A
      self.room_B = room_B
      self.room_C = room_C
      self.room_D = room_D 

      #information of resturant
      self.food_pay = food_pay
      self.Dessert = Dessert
      self.Drink = Drink
      self.Breakfast = Breakfast
      self.Lunch = Lunch
      self.Dinner = Dinner

      #Display function
      self.total_pay = total_pay

      #guess game 
      self.guees_user_point = guess_user_point
      self.guees_bot_point = guess_bot_point

      #rock paper scissor game
      self.rps_user_score = rps_user_score
      self.rps_bot_score = rps_bot_score


   #cin user information 
   def information(self):
      print("--- Wellcom to Hotel ---")
      self.name = input("Enter your fullname : ")
      self.sexual = input("Enter your sexual : (man / women) ")
      self.address = input("Enter your address : ")
      self.cindate = input("Enter your check in date : ")
      self.coutdate = input("Enter your check out date : ")
      
      if self.sexual == "man":
         print(f"--- Mr {self.name.upper()} information is --- ")
         print(f"name : {self.name} \nsexual : {self.sexual} \naddress : {self.address} \ncindate : {self.cindate} \ncoutdate : {self.coutdate}".upper())
      elif self.sexual == "woman":
         print(f"--- Miss {self.name.upper()} information is --- ")
         print(f"name : {self.name} \nsexual : {self.sexual} \naddress : {self.address} \ncindate : {self.cindate} \ncoutdate : {self.coutdate}".upper())
      
      else:
         print(f"name : {self.name} \nsexual : {self.sexual} \naddress : {self.address} \ncindate : {self.cindate} \ncoutdate : {self.coutdate}".upper())

   #roomrent ifromaton pay empty full room
   def roomrent(self):
      if self.sexual == "man":
         print(f"Mr {self.name.upper()} We have 100 rooms for you " )
      elif self.sexual == "women":
         print(f"Miss {self.name.upper()} We have this rooms for you " )
      while True:
         print(f"1.Class A romm ---> 400$ number of empty : {self.room_A}")
         print(f"2.Class B romm ---> 300$ number of empty : {self.room_B}")
         print(f"3.Class C romm ---> 200$ number of empty : {self.room_C}")
         print(f"4.Class D romm ---> 100$ number of empty : {self.room_D}")
         print("5.Exit")

         user_room_choice = int(input("Enter your Choice : "))
         user_day_choice = int(input("Enter How many days you want to stay :"))

         # Class A room
         if user_room_choice == 1:
            self.room_pay = self.room_pay + 400 * user_day_choice
            print(f"{self.name} choice Class A room for {user_day_choice} days\nroom number : {self.room_number} \nYour room bill {self.room_pay}")
            print(f"empty rooms : {self.empty_room} \nfull rooms : {self.full_room} \n ")
            self.empty_room -= 1
            self.full_room += 1
            self.room_number += 1
            self.room_A -= 1

         # Class B room
         elif user_room_choice == 2:
            self.room_pay = self.room_pay + 300 * user_day_choice
            print(f"{self.name} choice Class B room for {user_day_choice} days\nroom number : {self.room_number} \nYour room bill {self.room_pay} ")
            print(f"empty rooms : {self.empty_room} \nfull rooms : {self.full_room}")
            self.empty_room -= 1
            self.full_room += 1
            self.room_number += 1
            self.room_B -= 1

         #Class C room
         elif user_room_choice == 3:
            self.room_pay = self.room_pay + 200 * user_day_choice
            print(f"{self.name} choice Class C room for {user_day_choice} days\nroom number : {self.room_number} \nYour room bill {self.room_pay} ")
            print(f"empty rooms : {self.empty_room} \nfull rooms : {self.full_room}")
            self.empty_room -= 1
            self.full_room += 1
            self.room_number += 1
            self.room_C -= 1


         #Class D room
         elif user_room_choice == 4:
            self.room_pay = self.room_pay + 100 * user_day_choice
            print(f"{self.name} choice Class D room for {user_day_choice} days\nroom number : {self.room_number} \nYour room bill {self.room_pay} ")
            print(f"empty rooms : {self.empty_room} \nfull rooms : {self.full_room}")
            self.empty_room -= 1
            self.full_room += 1
            self.room_number += 1
            self.room_D -= 1


         elif user_room_choice == 5:
            break
   
   #information resturant 
   def resturant(self):
      while True:
         print("--- wellcom to restueant ---")
         print(f"1.Dessert ---> 1$  Available : {self.Dessert} ")
         print(f"2.Drink ---> 1$  Available : {self.Drink}")
         print(f"3.Breakfast ---> 5$  Available : {self.Breakfast}")
         print(f"4.Lunch ---> 7$  Available : {self.Lunch}")
         print(f"5.Dinner ---> 9$  Available : {self.Dinner}")
         print("6.Exit")

         user_food_request = int(input("Enter your number choice : "))
         user_quantity = int(input("Enter the quantity: "))

         #Dessert
         if user_food_request == 1:
            self.food_pay = self.food_pay + 1 * user_quantity
            print(f"You buy {user_quantity} from {self.Dessert} and your bill is : {self.food_pay}")
            self.Dessert -= user_quantity

         #Drink
         elif user_food_request == 2:
            self.food_pay = self.food_pay + 1 * user_quantity
            print(f"You buy {user_quantity} from {self.Drink} and your bill is : {self.food_pay}")
            self.Drink -= user_quantity

         #Breakfast
         elif user_food_request == 3:
            self.food_pay = self.food_pay + 5 * user_quantity
            print(f"You buy {user_quantity} from {self.Breakfast} and your bill is : {self.food_pay}")
            self.Breakfast -= user_quantity

         #Lunch
         elif user_food_request == 4 :
            self.food_pay = self.food_pay + 7 * user_quantity
            print(f"You buy {user_quantity} from {self.Lunch} and your bill is : {self.food_pay}")
            self.Lunch -= user_quantity
            
         #Dinner
         elif user_food_request == 5:
            self.food_pay = self.food_pay + 9 * user_quantity
            print(f"You buy {user_quantity} from {self.Dinner} and your bill is : {self.food_pay}")
            self.Dinner -= user_quantity

         elif user_food_request == 6:
            print(f"--- your food list is --- \n Dessert : {self.Dessert} \n Drink : {self.Drink} \n Breakfast : {self.Breakfast} \n Lunch : {self.Lunch} \n Dinner : {self.Dinner}")
            print(f"your bill is : {self.food_pay} \n Thanks for choice us")
            break

   #guess game for passenger
   def guess_game(self):
      print(f"--- wellcom to guess number game {self.name.upper()} ---")
      #cin level and loop of game from user
      level = int(input("Enter your level between 1 / 3 : "))
      

      # level 1 Guess 0 / 10
      if level == 1:
         loop = int(input("Enter loop of game : "))
         for i in range(1,loop+1):
            ai_choice1 = rn(1,10) 
            user = int(input("Guess number between 0 / 10 : "))
            if user == ai_choice1:
               self.guees_user_point += 1
               print(f"bot choice is {ai_choice1} and your choice is {user} and you win")
               print(f"{self.name.upper()} your score : {self.guees_user_point} \nbot score : {self.guees_bot_point} ")
               break
               
            else:
               self.guees_bot_point +=1
               print(f"bot choice is {ai_choice1} and your choice is {user} and you lost")
               print(f"{self.name} your score : {self.guees_user_point} \nbot score : {self.guees_bot_point} ")
               print(f"try again {self.name.upper()} ")
         #again function
               
            
      #level 2 Guess 0 / 20 
      elif level == 2:
         loop = int(input("Enter loop of game : "))
         for i in range(1,loop+1):
            ai_choice2 = rn(0,20)
            user = int(input("Guess number between 0 / 20 : "))
            if user == ai_choice2:
               self.guees_user_point += 1
               print(f"bot choice is {ai_choice2} and your choice is {user} and you win")
               print(f"{self.name.upper()} your score : {self.guees_user_point} \nbot score : {self.guees_bot_point} ")
               break
         
            else:
               self.guees_bot_point +=1
               print(f"bot choice is {ai_choice2} and your choice is {user} and you lost")
               print(f"{self.name} your score : {self.guees_user_point} \nbot score : {self.guees_bot_point} ")
               print(f"try again {self.name.upper()} ")
         #again function
               
      #level 2 Guess 0 / 30
      elif level == 3:
         loop = int(input("Enter loop of game : "))
         for i in range(1,loop+1):
            ai_choice3 = (0,30)
            user = int(input("Guess number between 0 / 30 : "))
            if user == ai_choice3 :
               self.guees_user_point += 1
               print(f"bot choice is {ai_choice3} and your choice is {user} and you win")
               print(f"{self.name.upper()} your score : {self.guees_user_point} \nbot score : {self.guees_bot_point} ")
               break

            else:
               self.guees_bot_point +=1
               print(f"bot choice is {ai_choice3} and your choice is {user} and you lost")
               print(f"{self.name} your score : {self.guees_user_point} \nbot score : {self.guees_bot_point} ")
               print(f"try again {self.name.upper()} ")
         #again function

      
      else:
         print("this level is not define")
         #again function


   #rock paper scissor game 
   def rockpaperscissor(self):
      print(f"wellcom to rock ... paper ... scissor game {self.name.upper()}")

      loop = int(input("enter loop of game : "))
      
      for i in range(1,loop+1):
         user = input("Enter your choice : ")
         number = rn(1,3)
         bot = ''
         if number == 1:
            bot = "rock"
            print("bot choice rock")
         elif number == 2:
            bot = "paper"
            print("bot choice paper")
         else:
            bot = "scissor"
            print("bot choice scissor")
         
         if user == "paper" and bot == "rock":
            self.rps_user_score +=1
            print(f"{self.name.upper()} you choice {user} and bot choice {bot} and you win \n{self.name.upper()} your score : {self.rps_user_score} \nbot score : {self.rps_bot_score}")
         elif user == "paper" and bot == "scissor":
            self.rps_bot_score +=1
            print(f"{self.name.upper()} you choice {user} and bot choice {bot} and you lost \n{self.name.upper()} your score : {self.rps_user_score} \nbot score : {self.rps_bot_score}")
         elif user == "rock" and bot == "paper":
            self.rps_bot_score +=1
            print(f"{self.name.upper()} you choice {user} and bot choice {bot} and you lost \n{self.name.upper()} your score : {self.rps_user_score} \nbot score : {self.rps_bot_score}")
         elif user == "rock" and bot == "scissor":
            self.rps_user_score += 1
            print(f"{self.name.upper()} you choice {user} and bot choice {bot} and you win \n{self.name.upper()} your score : {self.rps_user_score} \nbot score : {self.rps_bot_score}")
         elif user == "scissor" and bot == "paper":
            self.rps_user_score += 1
            print(f"{self.name.upper()} you choice {user} and bot choice {bot} and you win \n{self.name.upper()} your score : {self.rps_user_score} \nbot score : {self.rps_bot_score}")
         elif user == "scissor" and bot == "rock":
            self.rps_bot_score += 1
            print(f"{self.name.upper()} you choice {user} and bot choice {bot} and you lost \n{self.name.upper()} your score : {self.rps_user_score} \nbot score : {self.rps_bot_score}")
         elif user == "paper" and bot == "paper" or user == "rock" and bot == "rock" or user == "scissor" and bot == "scissor": 
            print(f"{self.name.upper()} you choice {user} and bot choice {bot} and equal \n{self.name.upper()} your score : {self.rps_user_score} \nbot score : {self.rps_bot_score}")
         else:
            print("--- this option is not define ---")
      #again function




   def Display(self):
      print("--- Custmer Hotel bill ---") 
      print(f"--- Custmer information --- \n fullname : {self.name} \n sexual : {self.sexual} \n address : {self.address} \n cindate : {self.cindate} \n coutdate : {self.coutdate} ")
      print(f"--- Custmer room rent --- \n {self.room_pay}")
      print(f"--- Custmer room number --- \n {self.room_number}")
      print(f"--- Custmer food \n {self.food_pay} ")

      self.total_pay = self.food_pay + self.room_pay

      print(f"Thank you for choosing us,{self.total_pay}$ it's your debt")
   
   

def main():

   a = Hotelmanage()

   while True:
      print("--- 1.Enter Customer Data ---")
            
      print("--- 2.Calculate Room Rent ---")

      print("--- 3.Calculate Food Purchased ---")
    
      print("--- 4.Show total cost ---")
    
      print("--- 5.Guess number game ---")

      print("--- 6.Rock ... Paper ... Scissor game ---")

      print("--- 7. Exit ---")

      user = int(input("\nEnter the number of your choice: "))
      
      if user == 1:
         a.information()

      elif user == 2:
         a.roomrent()
      
      elif user == 3:
         a.resturant()

      elif user == 4:
         a.Display()
      
      elif user == 5:
         a.guess_game()

      elif user == 6:
         a.rockpaperscissor()
      
      elif user == 7:
         break

      else:
         print("--- this option is not define ---") 

   
main()
