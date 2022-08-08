# start program

import math


reply_list1 = "Y", "YES"

#start of the  loop
start = input("Press Y or YES to start, else any key to quit: ")

while start.upper() in reply_list1:  
    while True:
        try:
            height = float(input("Enter The Height Of The Wall In Meter: "))    #get information if user enter anything beside numbers loop will be triggered  
            width = float(input("Enter The Width Of The  Wall In Meter: "))
            num_of_wall = int(input("Enter The Number Of Wall: "))
            break
        except ValueError:
            print("Please Type Numbers only!")
            continue
    
    repeat = input("Type Y or YES to retype , else any key to continue: ")

    if repeat.upper() in reply_list1:    # if user enter wrongly they can retype
        continue
    
    area = height * width * num_of_wall   # calculate the area
    print("The Total Area is", format(area, ',.2f') + " meter square")
    print("")

    while True:
        print("Please Choose a Type of Tile Stated Below")   
        print("1. Small Black Granite= 001 \n2. Medium Sunset Yellow= 002 \n3. Large Oak Wood Effect= 003 \n4. Extra-large White Marble= 004") # user tile selection
        tiles = input("Enter the Code of the Tile Wanted: ")
        print("")

        price_of_t1, price_of_t2, price_of_t3, price_of_t4 = 85.50, 55.00, 286.00, 290.00   #assign price to the tiles
        num_box1, num_box2, num_box3, num_box4 = math.ceil(area), math.ceil(area), math.ceil(area), math.ceil(area)  # round up to integar if has decimal

        code_list1 = "001", "1", "01"  # Creates possible customer's answers
        code_list2 = "002", "2", "02"
        code_list3 = "003", "3", "03"
        code_list4 = "004", "4", "04"
 
        # if else statement
        if tiles in code_list1:      
            print("The Total Price for Small Black Granite is RM" + str(format(price_of_t1 * num_box1, ",.2f")))
            print("Number Of Boxes Needed Are", num_box1)
            break
        elif tiles in code_list2:
            print("The Total Price for Medium Sunset Yellow is RM" + str(format(price_of_t2 * num_box2, ",.2f")))
            print("Number Of Boxes Needed Are", num_box2)
            break
        elif tiles in code_list3:
            print("The Total Price for Large Oak Wood Effect is RM" + str(format(price_of_t3 * num_box3, ",.2f")))
            print("Number Of Boxes Needed Are", num_box3)
            break
        elif tiles in code_list4:
            print("The Total Price for Extra-large White Marble is RM" + str(format(price_of_t4 * num_box4, ",.2f")))
            print("Number Of Boxes Needed Are", num_box4)
            break
        else:
            print("Please type the stated code!")
            continue
    print("")
    end = input("Type Y or YES to continue, else any key to end: ")  
 
    if end.upper() in reply_list1:    # if end variable get "y" will repeat all this loop
        continue
    else:
        break

if start.upper() != reply_list1:
    print("Thank You and have a nice day") #end program
