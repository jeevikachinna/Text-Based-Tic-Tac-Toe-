# Text-Based-Tic-Tac-Toe-
Tic-Tac-Toe is a classic two-player game where players take turns marking spaces in a 3×3 grid with "X" or "O". The first player to get three of their symbols in a row (vertically, horizontally, or diagonally) wins. If all spaces are filled and no player has won, it ends in a draw.

REQIREMENTS
 Python only (no extra libraries)

▶️ HOW TO RUN 

 Open your terminal or command prompt
 
 Navigate to the folder where the file is saved

 Save the code in a file like tic_tac_toe_text.py
 
 Run:
 python tic_tac_toe_text.py
 
def print_board(board):
    for row in board:
        print(" | ".join(row))
        print("-" * 5)

def check_win(board, player):
    for row in board:
        if all(s == player for s in row):
            return True
    for col in range(3):
        if all(row[col] == player for row in board):
            return True
    if all(board[i][i] == player for i in range(3)) or \
       all(board[i][2 - i] == player for i in range(3)):
        return True
    return False

def board_full(board):
    return all(cell != " " for row in board for cell in row)

def main():
    board = [[" " for _ in range(3)] for _ in range(3)]
    current_player = "X"

    while True:
        print_board(board)
        print(f"Player {current_player}'s turn.")
        row = int(input("Enter row (0-2): "))
        col = int(input("Enter col (0-2): "))

        if board[row][col] != " ":
            print("Cell already taken. Try again.")
            continue

        board[row][col] = current_player

        if check_win(board, current_player):
            print_board(board)
            print(f"🎉 Player {current_player} wins!")
            break

        if board_full(board):
            print_board(board)
            print("It's a tie!")
            break

        current_player = "O" if current_player == "X" else "X"

if __name__ == "__main__":
    main()
    
SAMPLE OUTPUT 
   |   |  
 -----
   |   |  
 -----
   |   |  
 Player X's turn.
 Enter row (0-2): 0
 Enter col (0-2): 1
 ...
 🎉 Player X wins!
🔄 Want to Extend It?
You can add:

🔁 Play Again Option

🧠 AI opponent (easy or smart)

⏱️ Timer for moves

✅ Input validation with retry

