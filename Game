# -----------------------------------------
# TIC-TAC-TOE GAME IN PYTHON
# -----------------------------------------

# Create the game board.
# Initially, each position contains its index (0-8).
# Later, players replace these numbers with X or O.
board = ["0", "1", "2",
        "3", "4", "5",
        "6", "7", "8"]


# -----------------------------------------
# Function: display()
# Purpose: Print the current board.
# -----------------------------------------
def display():

   # Print an empty line for better readability.
   print()

   # First row
   print(board[0], "|", board[1], "|", board[2])

   # Separator line
   print("--+---+--")

   # Second row
   print(board[3], "|", board[4], "|", board[5])

   # Separator line
   print("--+---+--")

   # Third row
   print(board[6], "|", board[7], "|", board[8])

   print()


# -----------------------------------------
# Function: player_move(player)
# Purpose:
# Take input from the current player.
# Validate the input.
# Update the board.
# -----------------------------------------
def player_move(player):

   # Continue asking until a valid move is entered.
   while True:

       try:

           # Ask player to enter a position.
           pos = int(input(f"Player {player}, Enter position (0-8): "))

           # Check whether position is inside the board.
           if pos < 0 or pos > 8:
               print("Invalid position.")
               continue

           # Check if the selected position is free.
           if board[pos] not in ["X", "O"]:

               # Place player's symbol.
               board[pos] = player

               # Exit loop after successful move.
               break

           else:
               print("Position already occupied.")

       # If user enters letters instead of numbers.
       except ValueError:
           print("Enter a valid number.")


# -----------------------------------------
# Function: check_winner(player)
# Purpose:
# Check if current player has won.
# Returns:
# True -> Player wins
# False -> No win
# -----------------------------------------
def check_winner(player):

   # List of all possible winning combinations.
   wins = [

       # Horizontal rows
       [0, 1, 2],
       [3, 4, 5],
       [6, 7, 8],

       # Vertical columns
       [0, 3, 6],
       [1, 4, 7],
       [2, 5, 8],

       # Diagonals
       [0, 4, 8],
       [2, 4, 6]
   ]

   # Check each winning combination.
   for combo in wins:

       # Compare three positions.
       if board[combo[0]] == board[combo[1]] == board[combo[2]] == player:
           return True

   # No winning combination found.
   return False


# -----------------------------------------
# Function: check_draw()
# Purpose:
# Check whether all positions are filled.
# Returns:
# True -> Draw
# False -> Game continues
# -----------------------------------------
def check_draw():

   # Check every cell.
   for cell in board:

       # If any number remains,
       # game is not over.
       if cell not in ["X", "O"]:
           return False

   # All positions occupied.
   return True


# -----------------------------------------
# Main Game Starts Here
# -----------------------------------------

# First player is X.
current = "X"

# Infinite loop until game ends.
while True:

   # Display board.
   display()

   # Ask current player for move.
   player_move(current)

   # Check whether current player wins.
   if check_winner(current):

       # Show final board.
       display()

       print(f"Player {current} Wins!")

       # Exit game.
       break

   # Check draw.
   if check_draw():

       display()

       print("Game Draw!")

       break

   # Change player.
   if current == "X":
       current = "O"
   else:
       current = "X"
