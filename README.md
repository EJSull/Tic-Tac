# Tic-Tac
Tic-Tac-Toe game
print("Welcome to the Amazing Tic Tac Toe Game!")
first_player = input("What is your name first player?")
Second_player = input("What is your name second player?")
print(f"Awesome! {first_player} is the first player and {Second_player} is the second player!")
print("Good luhc, have fun!")

def main():
    player = next_player("")
    board = create_board()
    while not (has_winner(board) or is_a_draw(board)):
        display_board(board)
        make_move(player, board)
        player = next_player(player)
    display_board(board)
    print("Congratulation!!!") 


def create_board():
    board = []
    for square in range(16):
        board.append(square + 1)
    return board

def display_board(board):
    print()
    print(f"{board[0]}|{board[1]}|{board[2]}|{board[3]}")
    print('-+-+-+-')
    print(f"{board[4]}|{board[5]}|{board[6]}|{board[7]}")
    print('-+-+-+-')
    print(f"{board[8]}|{board[9]}|{board[10]}|{board[11]}")
    print('-+-+-+-')
    print(f"{board[12]}|{board[13]}|{board[14]}|{board[15]}")
    print()

def is_a_draw(board):
    for square in range(16):
        if board[square] != "x" and board[square] != "o":
            return False
    return True 
    
def has_winner(board):
     return (board [0] == board [1] == board [2] == board [3] or
             board [4] == board [5] == board [6] == board [7] or
             board [8] == board [9] == board [10] == board [11] or
             board [12] == board [13] == board [14] == board[15] or
             board [0] == board [4] == board [8] == board [12] or 
             board [1] == board [5] == board [9] == board [13] or
             board [2] == board [6] == board [10] == board [14] or
             board [3] == board [7] == board [11] == board [15] or
             board [0] == board [5] == board [10] == board [15] or
             board [3] == board [6] == board [9] == board [12])

def make_move(player, board):
    square = int(input(f"{first_player}'s turn to select a square (1-16): "))
    square = int(input(f"{Second_player}'s turn to select a square (1-16): "))
    board[square - 1] = player

def next_player(current):
    if current == "" or current == "o":
        return 'x'
    elif current == "x":
        return 'o'

if __name__ == "__main__":
    main()
