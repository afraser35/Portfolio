# Portfolio
def printGrid(puzzle, grid):

    #
    # PRINT THE GAME GRID TO THE CONSOLE
    #

    # Begin by creating a new two-dimensional array for the box numbers
    
    boxnumbers = [[0 for x in range(15)] for x in range(15)]

    # Next, loop through all the words in the puzzle to get the box numbers

    for i in puzzle:

        # Get the next word in the puzzle

        nextword = puzzle[i];

        # Retrieve the X and Y of the first letter, along with the box number

        x = int(nextword['x'])
        y = int(nextword['y'])
        box = int(nextword['box'])

        # Add the box number to the array

        boxnumbers[y][x] = box

    # Now, print the grid to the console

    for y in range(0,15):

        # Print the top border of the next row, box by box

        for x in range(0, 15):

            # If there is no box number on this box, print an empty top

            if ( boxnumbers[y][x] == 0 ):
                sys.stdout.write('+---')

            # If there is a single-digit box number, print it in the center
            
            elif ( boxnumbers[y][x] < 10 ):
                sys.stdout.write('+-' + str(boxnumbers[y][x]) + '-')

            # If there is a double-digit box number, print it at the left edge
                
            elif ( boxnumbers[y][x] >= 10 ):
                sys.stdout.write('+' + str(boxnumbers[y][x]) + '-')

        # End the top border and begin printing the next row
        
        sys.stdout.write('+\n|')

        # Print the next row, box by box, padding each letter with spaces

        for x in range(0,15):

            sys.stdout.write(' ' + grid[y][x] + ' |')

        print()

    # Print the bottom border for the grid

    print('+' + '---+' * 15)

    
main()

