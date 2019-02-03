# DBhashmapAssignment
Simple index-based hashmap Datebase 

Simple DB hashmap in Google colab

Require that you have a Google account to sign in

Open the site URL for Google colab: https://colab.research.google.com/notebooks/welcome.ipynb 
1.	Go to File button on the top menu bar and select new Python 3 notebook
2.	Copy paste the following code: 

def write_tofile(keypair):
    file2 = open("textvalue.txt","a+")    
    file2.write(f"{str(keypair)}\n")
    
def insert(a,b):    
    pair = a,b
    write_tofile(pair)   
    print("Inserted " + a,b)

3.	Press on the arrow to the left to run the cell.
4.	Go to Insert button on the top bar and select code cell
5.	Copy paste the next lines and press on the arrow to the left to run the cell.


insert("1","Knud")
insert("2","sussie")
insert("3","Lena")
insert("4","Jens")
insert("6","jakob")
insert("9","Benjamin")
insert("10","Bent")
insert("10","Pernille")
insert("12","Sune")
insert("13","Klaus")
insert("15","Morten")
insert("16","Benny")
insert("17","Stine")
insert("18","Mia")
insert("20","Simon")
insert("110","Dorthe")


6.	Copy paste the next lines and press on the arrow to the left to run the cell.

def getvalue(key):
    hashmap = {} 
   
    character = 0   
    numberOfLines = 0

    getfile = open("textvalue.txt","r") 
   
    for line in getfile:
        
        extractId = line.split(',')
        unique = extractId[0]
        unique = unique.replace('(','')
        unique = unique.replace('\'','')
        name = extractId[1]
       
        name_length = len(name)
        
        eachline = line.split()
        numberOfLines += 1
        character += len(line)
        
        hashmap[unique]=character+1      
        
        if key == unique:
            key = str(key)
           
            end = hashmap[key]
            strpos = end - name_length                 
            match = line[:end]                        
            #print(match)
            
            div = match.split(',')
            name = div[1]
            name = name.replace('\'','')
            name = name.replace(')','')
            
            print(name)
       

7.	Try retrieving data with the next code (you can try any arbitrary number you have inserted previously):

getvalue('6')


8.	You can try insert new id number and names:

insert("100","xxxx")

