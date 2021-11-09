class Food(object):
    def __init__(self, item, price):
        self.item = item
        self.price = price
    
    def getprice(self):
        return self.price
    
    def __str__(self):
        return self.item + ' : ' + str(self.getprice())
        
# items
items = ['Small Breakfast Deal', 'Regular Breakfast Deal', 'Big Breakfast Deal', 'Or  Select individual food and bevarages items', 'egg', 'toast', 'coffee', 'tea']

# prices
costs = ["$10", "$20", "$30", 0, "$0.99 each", "0.79 per slice", "$1.09 per cup", "$0.89 per cup"]
prices = [10, 20, 30, 0, 0.99, 0.79, 1.09, 0.89]
selecteditems = []
totalprice = 0
itemcount = 0

def buildmenu(items, costs):
    menu = []
    for i in range(len(items)):
        menu.append(Food(items[i], costs[i]))
    return menu

def displaymenu(Foods):
    n = 1
    for el in Foods:
        if n == 4:
            print (el)
        else:
            print(n,'. ', el)
        n = n + 1
        
Foods = buildmenu(items, costs)


loop=True      
  
while loop:  
    ## While loop which will keep going until loop = False
    print("---------------------------------------------")
    print("  Welcome to the MIT Brekly! Restuarant")
    print("---------------------------------------------")
    displaymenu(Foods)    ## Displays menu
    choice=int(input("<Enter '000' to quit. Enter '111' to finalize for payment.>"))
    
    if choice==1:     
        print ("Menu 1 has been selected")
        selecteditems.append("Small Breakfast Deal")
        itemcount = itemcount + 1
        ## You can add your code or functions here
    elif choice==2:
        print ("Menu 2 has been selected")
        selecteditems.append("Regular Breakfast Deal")
        itemcount = itemcount + 1
        ## You can add your code or functions here
    elif choice==3:
        print ("Menu 3 has been selected")
        selecteditems.append("Big Breakfast Deal") 
        itemcount = itemcount + 1
        ## You can add your code or functions here
    elif choice==5:
        print ("Menu 5 has been selected")
        selecteditems.append("egg") 
        itemcount = itemcount + 1
        ## You can add your code or functions here
    elif choice==6:
        print ("Menu 6 has been selected")
        selecteditems.append("toast") 
        itemcount = itemcount + 1
    elif choice==7:
        print ("Menu 7 has been selected")
        selecteditems.append("coffee") 
        itemcount = itemcount + 1
    elif choice==8:
        print ("Menu 8 has been selected")
        selecteditems.append("tea") 
        itemcount = itemcount + 1
    elif choice==000:
        print("Goodbye")
        loop=False # This will make the while loop to end as not value of loop is set to False
    elif choice==111:
        loop=False
        print("Order Finalize")
        print("-----------------------")
        print("Items selected --- "+str(itemcount))
        for item in selecteditems:
            print(item)
            index = items.index(item)
            itemprice = prices[index]
            totalprice = totalprice + itemprice
        print("Total = $"+str(totalprice) )
    else:
        # Any integer inputs other than values 1-5 we print an error message
        print("Wrong option selection. Enter any key to try again..")
