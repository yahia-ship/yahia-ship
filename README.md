print("before use this code go to terminal window and enter: 'pip install colorama' and enjoy")
from colorama import Fore, Style
print (Fore.GREEN + "welcome user")
while True:
    procesing = input (Fore.BLUE + "what user whant enter '1' to calculator or '2' to exit or '3' to notes: ")
    if procesing == '2':
        print (Fore.GREEN + "good bye")
        break
    elif procesing == '1':
        num01 = input (Fore.YELLOW + "enter first number from 1 to 9: ")
        procesing2 = input ("enter '+' to Addition or '-' to Subtraction or '/' to Division or '*' to Multiplication or '**' to Exponentiation: ")
        num02 = input (Fore.YELLOW +  "enter second number from 1 to 9: ")
        try:
            num01 = float(num01)
            num02 = float(num02)
        except ValueError:
            print(Fore.RED + "Error: Please enter valid numbers!")
            continue
        if procesing2 == '+':
            result =num01 + num02
            print(Fore.GREEN + "your result is: " + str(result))
        elif procesing2 == '-':
            result = num01 + num02
            print(Fore.GREEN + "your result is: " + str(result))
        elif procesing2 == '/':
            if num02 == 0:
                print(Fore.RED + "please dont enter num 0 for division!")
            else:
                result = num01 / num02
                print (Fore.GREEN + "your result is: " + str(result))
        elif procesing2 == '*':
            result = num01 * num02
            print(Fore.GREEN + "your result is: " + str(result))
        elif procesing2  == '**':
            result = num01 ** num02
            print(Fore.GREEN + "your result is: " + str(result))
        else:
            print(Fore.RED + "eror: choise not find!")
        user_choise = input(Fore.LIGHTBLACK_EX + "you want to continue: yes/no: ").lower()
        if user_choise == 'yes':
            continue
        elif user_choise == 'no':
            print(Fore.GREEN + "good bye")
            break
        else:
            print(Fore.RED + "eror: choise not find!")
    elif procesing == '3':
        filename = "notes.txt"
        while True:
            print(Fore.LIGHTBLACK_EX +  "Choose one:\n")
            print(Fore.LIGHTBLACK_EX +  "1 to add a note")
            print(Fore.LIGHTBLACK_EX +  "2 to read the notes")
            print(Fore.LIGHTBLACK_EX +  "3 to exit")

            choice = input(Fore.YELLOW + "Enter your choice: ")

            if choice == '1':
                note = input(Fore.LIGHTYELLOW_EX + "Enter your note: ")
                with open(filename, "a") as file:
                    file.write(note + "\n")
                print(Fore.GREEN + "Note saved successfully!")

            elif choice == '2':
                try:
                    with open(filename, "r") as file:
                        content = file.read()
                        if content:
                            print(Fore.GREEN + "\nSaved notes:")
                            print(content)
                        else:
                            print( Fore.RED + "No notes found!")
                except FileNotFoundError:
                    print(Fore.RED + "Error: File not found. Add a note first!")

            elif choice == '3':
                print(Fore.GREEN + "Exiting notes...")
                break
        else:
            print(Fore.RED + "error:choice not find!")


    else:
        print(Fore.RED + "eror: choise not find!")
        continue
