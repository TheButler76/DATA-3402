```python
# Variables represent spaces on the checker board.
empty=0
## game board size
size=8

# Chess Piece dictionary. 
"""
Here, the chess pieces are ordered in a list.
The values of this dictionary has to be a list,
so that we can use loop logic.
"""
Pieces = { 
    "White": ["WP", "WR", "WN", "WB", "WQ", "WK"],
    "Black": ["BP", "BR", "BN", "BB", "BQ", "BK"]
}
```


```python
def create_board(size):
    # Creates an empty 8x8 board
    board=[[empty]*size for i in range(size)]

    # Loops through the dict and appends chess pieces to their place on the 8x8 board.
    for color in Pieces.keys():
        if color == "Black":
            # Sets Pawns in place.
            board[1]=[Pieces[color][0] for i in range(size)]
    
            # Sets other chess pieces in place using list slicing.
            board[0][0:8:7]=[Pieces[color][1] for i in range(2)]
            board[0][1:7:5]=[Pieces[color][2] for i in range(2)]
            board[0][2:6:3]=[Pieces[color][3] for i in range(2)]
            board[0][3]=Pieces[color][4]
            board[0][4]=Pieces[color][5]
            
        if color == "White":
            # Sets Pawns in place.
            board[-2]=[Pieces[color][0] for i in range(size)]
            
            # Sets other chess pieces in place using list slicing.
            board[7][0:8:7]=[Pieces[color][1] for i in range(2)]
            board[7][1:7:5]=[Pieces[color][2] for i in range(2)]
            board[7][2:6:3]=[Pieces[color][3] for i in range(2)]
            board[7][3]=Pieces[color][4]
            board[7][4]=Pieces[color][5]
    return board
create_board(size)
```




    [['BR', 'BN', 'BB', 'BQ', 'BK', 'BB', 'BN', 'BR'],
     ['BP', 'BP', 'BP', 'BP', 'BP', 'BP', 'BP', 'BP'],
     [0, 0, 0, 0, 0, 0, 0, 0],
     [0, 0, 0, 0, 0, 0, 0, 0],
     [0, 0, 0, 0, 0, 0, 0, 0],
     [0, 0, 0, 0, 0, 0, 0, 0],
     ['WP', 'WP', 'WP', 'WP', 'WP', 'WP', 'WP', 'WP'],
     ['WR', 'WN', 'WB', 'WQ', 'WK', 'WB', 'WN', 'WR']]




```python
# We can create a fresh board by initializing a new variable
board=create_board(size)
board
```




    [['BR', 'BN', 'BB', 'BQ', 'BK', 'BB', 'BN', 'BR'],
     ['BP', 'BP', 'BP', 'BP', 'BP', 'BP', 'BP', 'BP'],
     [0, 0, 0, 0, 0, 0, 0, 0],
     [0, 0, 0, 0, 0, 0, 0, 0],
     [0, 0, 0, 0, 0, 0, 0, 0],
     [0, 0, 0, 0, 0, 0, 0, 0],
     ['WP', 'WP', 'WP', 'WP', 'WP', 'WP', 'WP', 'WP'],
     ['WR', 'WN', 'WB', 'WQ', 'WK', 'WB', 'WN', 'WR']]


