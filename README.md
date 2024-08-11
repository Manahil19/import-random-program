# import-random-program
import random
def madedict():
    with open("CountryCapital.txt","r") as f:
        dictionary={}
        first=f.readline()
        while first!="":
            modify=first.split(",")
            country=modify[0]
            capital=modify[1]
            capital.rstrip("\n")
            dictionary[country]=capital
            first=f.readline()
#         print(dictionary)
        x=dictionary.values()
#         print(x)
        list123=[]
        for i in x:
                i=i.rstrip("\n")
                list123.append(i)
#         print(list123)
            
        count=1
        num=int(input("\nHow many question you want to attempt: "))
        total=0
        while count<=num:
            random_capital=random.choice(list(dictionary.keys()))
            print(f"\n{count} Guessed Country is: {random_capital}")
            answer=input("\nEnter Country Correct Capital: ")
            answer=answer.capitalize()
            if answer in list123:
                print("\n--> Correct Answer.")
                total+=10
                dictionary.pop(random_capital)
            else:
                print("\n--> Incorrect Answer.")
                total-=5
            print("-----------------------------------------------")
            count+=1
             
        print("\n--> Total Attempts Made: ",num)
        print("--> Total Marks Got: " ,total)
        print("-----------------------------------------------")

madedict()
