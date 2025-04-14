## Objective : 
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

## Solution : 
The password is "7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4". 
by running the command : `tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt` 

## Explanation : 
- **`tr`**: The command-line utility for translating characters.
    
- **`'A-Za-z'`**: This is the **set of characters you want to replace**.
    
    - `A-Z` is all **uppercase** letters.
        
    - `a-z` is all **lowercase** letters.
        
    - So together, it means: "look at every alphabetic character."
        
- **`'N-ZA-Mn-za-m'`**: This is the **replacement set**.
    
    - `N-ZA-M`: This shifts **uppercase** letters 13 positions forward in the alphabet (wrapping around after Z).
        
        - Example: A → N, B → O, ..., M → Z, N → A, ..., Z → M
            
    - `n-za-m`: Same thing for **lowercase** letters.
        
- **`< data.txt`**: Redirects the contents of `data.txt` **as input to `tr`**.