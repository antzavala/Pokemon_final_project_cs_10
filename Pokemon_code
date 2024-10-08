# import libraries 
import random
import math 
import time

#set up pokeomon class    
class Pokemon: 
    def __init__(self, name, type, strength, hp):
        self.name = name 
        self.type = type 
        self.strength = strength
        self.hp = hp
        
#initialize pokemon 

Torchic = Pokemon("Torchic", "fire", 60, 45)

Mudkip = Pokemon("Mudkip", "water", 70, 50)

Cherubi = Pokemon("Cherubi", "grass", 45, 35)

Staryu = Pokemon("Staryu", "water", 45, 30)

Oddish = Pokemon("Oddish", "grass", 50, 45)

Vulpix = Pokemon("Vulpix", "fire", 41, 38)

Piplup = Pokemon("Piplup", "water", 51, 53)

Chimchar = Pokemon("Chimchar", "fire", 58, 44)

Snivy = Pokemon("Snivy", "grass", 45, 45)

copy_s = Pokemon("copy_s", "none", 0, 0)

copy_o = Pokemon("copy_o", "none", 0, 0)


#sets list of all the pokemon     
pokemon_list = [Torchic, Mudkip, Cherubi, Staryu, Oddish, Vulpix, Piplup, Chimchar, Snivy]

#sets lists of pokemon of wach of the different types 
fire_gym = [Vulpix, Chimchar, Torchic]
water_gym = [Piplup, Staryu, Mudkip]
grass_gym = [Cherubi, Snivy, Oddish] 
starter = Snivy
TA_list = ["Vendansh", "Victoria", "Stacy"]


#Greets the user
print("Hello, welcome to the game. I'm Professor Garcia. Type 'Start()' to begin")

#starts the game
def Start():
    #allows the player to be randomly assigned a pokemon
    starter = random.choice(pokemon_list) 
    time.sleep(1)
    print("Your starter is ", starter.name)
    time.sleep(1)
    print("To choose your gym choose water, fire, or grass")

    #allows the player to ask for help
    

    #sets up game 
    game_over = False 
    while game_over == False :
        #initialize user score 
        player_score = 0 
        opponent_score = 0 
        time.sleep(1)
        #sets conditions for the game to end 
        if player_score >= 2:
            game_over = True
            return "Game over. You win! Type Start() to play again"
        if opponent_score >= 2: 
            game_over = True 
            return "Game over. You lose! Type Start() to play again" 
        text = input('enter text: ') 
        return choose_gym(text, opponent_score, player_score) 
        


def choose_gym(gym, opponent_score, player_score): 
    #this block allows the player to choose a gym, and randomly assigns them a pokemon corresponding to that gym
    #the fire gym contains only fire type pokemon, the water gym only contains water type, etc. 
    time.sleep(1)
    if gym == "water": 
        opponent = random.choice(water_gym)
    elif gym == "fire":
        opponent = random.choice(fire_gym)
    elif gym == "grass":
        opponent = random.choice(grass_gym)
    else:
        print("Whoops! looks like you typed the wrong word. The options are fire, water, or grass!")
        text = input('enter text: ')
        return choose_gym(text, opponent_score, player_score)
    print("Your opponent is", opponent.name)
    return fight(opponent, starter, opponent_score, player_score)

#creates a copy of a pokemon which can be changed without changing the actual pokemon's stats
def copy(pokemon): 
    copy.name = pokemon.name
    copy.strength = pokemon.strength 
    copy.type = pokemon.type
    copy.hp = pokemon.hp
    


'''def type_impact(opponent, starter): 
   #this block takes in the player's and opponent's respective pokemon types and adjusts the strength of one of them based on each of their types  
   copy_s = copy(starter)
   copy_s.strength = starter.strength
   copy_o = copy(opponent) 
   copy_o.strength = opponent.strength
   if opponent.type == starter.type: 
       copy_s.strength = starter.strength 
       copy_o.strenght = opponent.strength
   elif opponent.type == "fire" and starter.type == "water": 
        copy_o.strength = (opponent.strength / 2)
   elif opponent.type == "fire" and starter.type == "grass": 
        copy_s.strength = (starter.strength /2)
   elif opponent.type == "water" and starter.type == "fire": 
       copy_s.strength = (starter.strength / 2)
   elif opponent.type == "water" and starter.type == "grass": 
       copy_o.strength = (opponent.strength / 2)
   elif opponent.type == "grass" and starter.type == "water": 
       copy_s.strength = (starter.strength / 2)
   elif opponent.type == "grass" and starter.type == "fire": 
       copy_o.strength = (opponent.strength / 2)'''
 
   

def fight(opponent, starter, opponent_score, player_score):
    #this block takes in the opponent and starter pokemon and determines how many strikes it would take to beat the other 
    #based on their respective strengths and hps, as well as the results of the type_impact block

    #assigns the copy the attributes of the starter pokemon
    copy_s.name = starter.name 
    copy_s.type = starter.type
    copy_s.hp = starter.hp
    copy_s.strength = starter.strength 

    #assigns the copy the attributes of the opponent pokemon
    copy_o.name = opponent.name 
    copy_o.type = opponent.type
    copy_o.hp = opponent.hp
    copy_o.strength = opponent.strength 

    if opponent.type == starter.type: 
       copy_s.strength = starter.strength 
       copy_o.strength = opponent.strength
    elif opponent.type == "fire" and starter.type == "water": 
        copy_o.strength = (opponent.strength / 2)
    elif opponent.type == "fire" and starter.type == "grass": 
        copy_s.strength = (starter.strength /2)
    elif opponent.type == "water" and starter.type == "fire": 
       copy_s.strength = (starter.strength / 2)
    elif opponent.type == "water" and starter.type == "grass": 
       copy_o.strength = (opponent.strength / 2)
    elif opponent.type == "grass" and starter.type == "water": 
       copy_s.strength = (starter.strength / 2)
    elif opponent.type == "grass" and starter.type == "fire": 
       copy_o.strength = (opponent.strength / 2)
    else: 
        return "combination isn't in here"

    opponent_hits = starter.hp / copy_o.strength 
    starter_hits = opponent.hp / starter.strength 
    starter_hits = math.floor(starter_hits)
    opponent_hits = math.floor(opponent_hits)
    time.sleep(1) 
    TA = random.choice(TA_list)
    print(TA, "says Go! You got this!") 
    if opponent_hits < starter_hits: 
        player_score += 1
        print("Starter wins the match!")
        time.sleep(1)
        print("The score is", player_score, opponent_score)

    if starter_hits < opponent_hits: 
        opponent_score += 1
        print("Opponent wins the match!")
        time.sleep(1)
        print("The score is", player_score, opponent_score)

    if opponent_hits == starter_hits:
        print("It's a Draw!")
        time.sleep(1)
        print("The score is", player_score, opponent_score)

    #Ends the game when someone scores 2/3
    if player_score >= 2:
            game_over = True
            time.sleep(1)
            return "Game over. You win!"
    
    if player_score == 1: 
        time.sleep(1)
        TA = random.choice(TA_list)
        print(TA, "says 'almost there!'") 
    if opponent_score >= 2: 
            time.sleep(1)
            game_over = True 
            return "Game over. You lose!" 
    if opponent_score ==  1: 
        TA = random.choice(TA_list)
        time.sleep(1)
        print(TA, "says Go! 'you'll get the next one!")
    if opponent_score < 2 and player_score < 2:
        time.sleep(2)
        print("Type 'fire', 'water', or 'grass' to choose a gym for the next round")
        text = input('enter text: ') 
        return choose_gym(text, opponent_score, player_score) 
