## Exercise: Python Dict and Tuples

1. We have following information on countries and their population (population is in crores),

    |Country|Population|
    |-------|----------|
    |China|143|
    |India|136|
    |USA|32|
    |Pakistan|21|
    1. Using above create a dictionary of countries and its population
    2. Write a program that asks user for three type of inputs,
        1. print: if user enter print then it should print all countries with their population in this format,
            ```
            china==>143
            india==>136
            usa==>32
            pakistan==>21
            ```
        1. add: if user input add then it should further ask for a country name to add. If country already exist in our dataset then it should print that it exist and do nothing. If it doesn't then it asks for population and add that new country/population in our dictionary and print it
        2. remove: when user inputs remove it should ask for a country to remove. If country exist in our dictionary then remove it and print new dictionary using format shown above in (a). Else print that country doesn't exist!
        3. query: on this again ask user for which country he or she wants to query. When user inputs that country it will print population of that country.


population_dic = {"China": 143,
                  "India":  136,
                  "Usa": 32,
                  "Pakistan": 21,
                  }

choice = input("What do you want to do? ").lower()
if choice == "print":
    for key in population_dic:
        value = population_dic[key]
        print(key, "==>", value)
if choice == "add":
    new_country = input("Name of country you want to add? ").title()
    if new_country in population_dic:
        print("Country already exist in directory")
    else:
        population = input(f"Enter Population for {new_country}: ")
        population_dic.update({new_country: population})
if choice == "remove":
    delete_country = input("What country do you want to delete").title()
    if delete_country in population_dic:
        del population_dic[delete_country]
    else:
        print("Country does not exist in database.")
if choice == "query":
    query_country = input("What country would you like to query? ").title()
    if query_country in population_dic:
        print(f"The population of {query_country} is: {population_dic[query_country]} ")
    else:
        print("Country does not exist in database.")


[Solution](https://github.com/codebasics/py/blob/master/Basics/Exercise/11_dict_tuples/11_dict_exercise_1_country_population.py)

2. You are given following list of stocks and their prices in last 3 days,

    |Stock|Prices|
    |-------|----------|
    |info|[600,630,620]|
    |ril|[1430,1490,1567]|
    |mtl|[234,180,160]|

    1. Write a program that asks user for operation. Value of operations could be,
        1. print: When user enters print it should print following,
            ```
            info ==> [600, 630, 620] ==> avg:  616.67
            ril ==> [1430, 1490, 1567] ==> avg:  1495.67
            mtl ==> [234, 180, 160] ==> avg:  191.33
            ```
        2. add: When user enters 'add', it asks for stock ticker and price. If stock already exist in your list (like info, ril etc) then it will append the price to the list. Otherwise it will create new entry in your dictionary. For example entering 'tata' and 560 will add tata ==> [560] to the dictionary of stocks.

stock_prices = {"info": [600, 630, 620],
                "ril": [1430, 1490, 1567],
                "mtl": [234, 180, 160],
}

choice = input("What operation do you want to perform? ")
if choice == "print":
    for key in stock_prices:
        value = stock_prices[key]
        size = len(value)
        average = round((sum(value)/size), 2)
        print(f"{key} == > {value} == > avg: {average}")
if choice == "add":
    stock_input = input("What is the Stock ticker you would like to add?").lower()
    price_input = int(input(f"Enter the price of {stock_input}: "))
    if stock_input in stock_prices:
        stock_prices[stock_input].append(price_input)
    elif stock_input not in stock_prices:
        stock_prices.update({stock_input: stock_prices})
else:
    print("You have entered the wrong operation. ")
        

[Solution](https://github.com/codebasics/py/blob/master/Basics/Exercise/11_dict_tuples/11_dict_exercise_2_stocks.py)

3. Write circle_calc() function that takes radius of a circle as an input from user and then it calculates and returns area, circumference and diameter. You should get these values in your main program by calling circle_calc function and then print them


def circle_calc(radius):
    area = round((3.14159265*(radius ^ 2)), 2)
    circumference = round((2*3.14159265*radius),2)
    diameter = round((circumference/3.14159265),2)
    return f"area = {area}, circumference = {circumference}, diameter = {diameter}"


print(circle_calc(6))
[Solution](https://github.com/codebasics/py/blob/master/Basics/Exercise/11_dict_tuples/11_dict_exercise_3_circle.py)
