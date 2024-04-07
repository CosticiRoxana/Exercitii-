# Exercitii-
Exercitii Python
""" Exercitii de pe codewars"""

def to_alternating_case(string):
    """ Transformarea literelor mici in litere mari si viceversa dintr-un string """

    stringAlternat = ""
    for litera in string:
        if litera.islower():
            stringAlternat += litera.upper()
        else:
            stringAlternat += litera.lower()
    return stringAlternat

print(to_alternating_case('HeLLo WoRLD'))

# A doua versiune a acestui exercitiu

def to_altenrating_case2(string):

    stringAlt = ''

    # iteram listaString cu for bucla
    for ind in range(len(string)):
        if string[ind].islower():
            stringAlt += string[ind].upper()
        else:
            stringAlt += string[ind].lower()

    return stringAlt

print(to_altenrating_case2('HeLLo WoRLD'))

# Eliminarea vocalelor mici aeiou


def shortcut(s):
    """ de eliminat vocalele mici aeiou """
    s2 = ''
    ref = 'aeiou'

    for litera in s:
        if litera not in ref:
            s2 += litera

    return s2

print(shortcut("HELLO"))

# Dublarea caracterelor intr-un string

def repeat_characters(input_string):
  return "".join([char * 2 for char in input_string])


def repeat_characters2(in_str):
  str = ''
  for litera in in_str:
      str += litera * 2
  return(str)


# Roxana

#def repeat_characters3(input_string):


# Complete the function that accepts a string parameter, and reverses each word in the string. All spaces in the
# string should be retained.

# "This is an example!" ==> "sihT si na !elpmaxe"
# "double  spaces"      ==> "elbuod  secaps"

def reverse_words(text):
    """ functie care inverseaza fiecare cuvant dintr-un string - propozitie si pastreaza spatiile """
    textRev = ''
    lista = text.split(' ')    # Metoda .split() sparge un string in elemente distincte pe care le introduce intr-o lista
                            # si le separa dupa ' ' (spatiu)
                            # daca avem parametru x .split(x), este folosit pentru a sparge string-ul la gairea lui x
    for cuvant in lista:
        lci = list(cuvant)  # spargem cuvantul in lista ca sa inversam ordinea lieterelor din cuvant
        lci.reverse()         # .reverse() este metoda care modifica structura liste initiale la apelare
        ci = "".join(lci)   # unim elementele din lista inapoi in string
        textRev += ci + ' '
    return textRev[:-1]


print(reverse_words('This is an example!'))
print(reverse_words('double  spaces'))


# Simple, given a string of words, return the length of the shortest word(s).
#
# String will never be empty and you do not need to account for different data types.

def find_short(s):
    """ de gasit cel mai scurt cuvant dintr-o propozitie """

    lista = s.split()

    listalen = []

    for cuvant in lista:
        listalen.append(len(cuvant))

    return min(listalen)

print(find_short('bitcoin take over the world maybe who knows perhaps'))


#   Your task is to create a function that does four basic mathematical operations.
#
# The function should take three arguments - operation(string/char), value1(number), value2(number).
# The function should return result of numbers after applying the chosen operation.
def basic_op(operator, value1, value2):

    # metoda compacta
    return eval(str(value1) + operator + str(value2))

print(basic_op('+', 4, 7))

# Info pentru functia eval(expresie string) - https://www.programiz.com/python-programming/methods/built-in/eval


# Implement the function unique_in_order which takes as argument a sequence and returns a list of items without any elements with the same value next to each other and preserving the original order of elements.

def unique_in_order(sequence):

  order = []

  if not sequence:
    return order

  order.append(sequence[0])
  for i in range(1,len(sequence)):
    if sequence[i-1] != sequence[i]:
      order.append(sequence[i])
  return order

print(unique_in_order('AAAABBBCCDAABBB'))


# Build a function that returns an array of integers from n to 1 where n>0.
# Example : n=5 --> [5,4,3,2,1]


def reverse_seq(n):
    lista = list(range(1, n + 1))     # creem un iterabil cu functia range cu valori de la 1 la n + 1 ca sa il includa
    # si pe n, dupa pasam acest iterabil in functia list ca sa stocam valorile produse de functia range in lista.
    lista.reverse()                   # apelam metoda .reverse() pe lista metoda care modifica forma listei inversand
    #ordinea elementelor din lista.
    return lista

print(reverse_seq(5))

# Given a non-empty array of integers, return the result of multiplying the values together in order. Example:
# [1, 2, 3, 4] => 1 * 2 * 3 * 4 = 24

def grow(arr):
    prod = 1                 # am  declarat o variabila, pt ca de la 1 incepem (orice nr inmultit cu 0 este 0)
    #daca puneam prod dupa for nu mai trecea de unu(pt ca bucla o ia si se reseta pe prob la 1 la fiecare iteratie)
    for n in arr:
        #prod = 1           #daca  il  bag aici mi-l blocheaza la 1 ! !!!! deci nu aici!!!!
        print(prod)      #
        prod *= n
    return prod

print(grow( [2, 2, 2, 2, 2, 2]))

# Summation
# Write a program that finds the summation of every number from 1 to num. The number will always be a positive integer
# greater than 0. Your function only needs to return the result, what is shown between parentheses in the example below
# is how you reach that result and it's not part of it, see the sample tests.
# For example (Input -> Output):
# 2 -> 3 (1 + 2)
# 8 -> 36 (1 + 2 + 3 + 4 + 5 + 6 + 7 + 8)

def summation(num):                                             #varianta lunga la sum()
    abcd = list(range(1, num + 1))
    adunari = 0     #aici scriem de lace nr incepe!!!
    for n in abcd:
        adunari += n # pe rand va lua fiecare n!!!!
    return adunari   #returnam ceea ce am dat ,,crestere''


print(summation(6))


def summation2(num):
    abcd = list(range(1, num + 1))
    return sum(abcd)                       # functia sum calculeaza suma elementelor numerice dintr- un array similar
#cu metoda for de la linia 188!


# Create a function that accepts a string and a single character, and returns an integer of the count of occurrences
# the 2nd argument is found in the first one.
# If no occurrences can be found, a count of 0 should be returned.
# ("Hello", "o")  ==>  1
# ("Hello", "l")  ==>  2
# ("", "z")       ==>  0
# str_count("Hello", 'o'); // returns 1
# str_count("Hello", 'l'); // returns 2
# str_count("", 'z'); // returns 0
# Notes
# The first argument can be an empty string
# In languages with no distinct character data type, the second argument will be a string of length 1


def str_count(strng, letter):
    aparitii = 0            # am creeat variabila aparitie ca sa  stocam numarul aparitiilor letter in strng
    for litera in strng:    # am interat fiecare litera in strng
        if litera == letter:  # am comparat daca litera egala cu letter
            aparitii += 1    # am incrementat variabila aparitii cu valoarea 1

    return aparitii         #am returnat aparitiile (unde s -au stocat)


print(str_count('hello', 'l'))


# The Story:
# Bob is working as a bus driver. However, he has become extremely popular amongst the city's residents.
# With so many passengers wanting to get aboard his bus, he sometimes has to face the problem of not enough space left
# on the bus! He wants you to write a simple program telling him if he will be able to fit all the passengers.
# Task Overview:
# You have to write a function that accepts three parameters:
# cap is the amount of people the bus can hold excluding the driver.
# on is the number of people on the bus excluding the driver.
# wait is the number of people waiting to get on to the bus excluding the driver.
# If there is enough space, return 0, and if there isn't, return the number of passengers he can't take.
# Usage Examples:
# cap = 10, on = 5, wait = 5 --> 0 # He can fit all 5 passengers
# cap = 100, on = 60, wait = 50 --> 10 # He can't fit 10 of the 50 waiting


def enough(cap, on, wait):
    loc_liber = cap - on         # am creat variabila loc liber in care am stocat diferenta dintre capacitatea
    # autobuzului si locurile ocupate
    if loc_liber >= wait:        # am pus conditia ca locurile libere sa fie mai mare sau egale cu pers care asteapta
        #in statie (wait)
        return 0                 # am returnat 0 pt ca locurile libere sunt mai mare sau egale cu wait
    else:
        return wait - loc_liber  #am facut diferenta dintre pers care ast(wait) si locurile libere ca sa aflam
    #cati oameni raman in statie

print(enough(100 , 60 , 50))


# Task:
# Your task is to write a function which returns the sum of following series upto nth term(parameter).
# Series: 1 + 1/4 + 1/7 + 1/10 + 1/13 + 1/16 +...
# Rules:
# You need to round the answer to 2 decimal places and return it as String.
#
# If the given value is 0 then it should return 0.00
#
# You will only be given Natural Numbers as arguments.
#
# Examples:(Input --> Output)
# 1 --> 1 --> "1.00"
# 2 --> 1 + 1/4 --> "1.25"
# 5 --> 1 + 1/4 + 1/7 + 1/10 + 1/13 --> "1.57"


def series_sum(n):
    numar = 1           # declaram variabila numar cu valoarea 1, care va asigura incrementarea cu valoarea 3
                        # a divizorului
    numartot = 0        # Variabila numartot va stoca adunarile operatiilor in functie de numarul n - operatii egale cu
                        # numarul n
    if n == 1:          # Eliminam situatia cand n = 1, ca sa putem returna un string cu doua zero dupa unu
        return '1.00'
    elif n == 0:
        return '0.00'
    for i in range(n):      #i = nr de iteratii - cream o bucla for cu parametru n - n iteratii ale buclei
        numartot += 1 / numar   # stocam in numartot rezultatul operatiei de impartire a lui 1 la numar
        numar += 3              # incrementam cu 3 valoarea lui numar pentru a respecta conditia operatiilor

    strnum = str(round(numartot, 2))

    if len(strnum) == 3:
        strnum += '0'

    return strnum  # rotunjim la doua zecimale numartot si dupa il transformam in string conform
                                    # cerintelor problemei

print(series_sum(500))


i = 0
while i <= 5:
    i += 1
    print(i)

# Write a function to split a string and convert it into an array of words.
#  Examples (Input ==> Output):
# "Robin Singh" ==> ["Robin", "Singh"]
#  "I love arrays they are my favorite" ==> ["I", "love", "arrays", "they", "are", "my", "favorite"]

def string_to_array(s):
    return list(s.split(" "))

#am dat return list si am cautat pe google sintaxa de split


# Complete the function that accepts a string parameter, and reverses each word in the string. All spaces in the
# string should be retained.

# "This is an example!" ==> "sihT si na !elpmaxe"
# "double  spaces"      ==> "elbuod  secaps"

def reverse_words(text):
    """ functie care inverseaza fiecare cuvant dintr-un string - propozitie si pastreaza spatiile """
    textRev = ''
    lista = text.split(' ')    # Metoda .split() sparge un string in elemente distincte pe care le introduce intr-o lista
                            # si le separa dupa ' ' (spatiu)
                            # daca avem parametru x .split(x), este folosit pentru a sparge string-ul la gairea lui x
    for cuvant in lista:
        lci = list(cuvant)  # spargem cuvantul in lista ca sa inversam ordinea lieterelor din cuvant
        lci.reverse()         # .reverse() este metoda care modifica structura liste initiale la apelare
        ci = "".join(lci)   # unim elementele din lista inapoi in string
        textRev += ci + ' '
    return textRev[:-1]


print(reverse_words('This is an example!'))
print(reverse_words('double  spaces'))


# Simple, given a string of words, return the length of the shortest word(s).
#
# String will never be empty and you do not need to account for different data types.

def find_short(s):
    """ de gasit cel mai scurt cuvant dintr-o propozitie """

    lista = s.split()

    listalen = []

    for cuvant in lista:
        listalen.append(len(cuvant))

    return min(listalen)

print(find_short('bitcoin take over the world maybe who knows perhaps'))


def positive_sum(arr):
    for element in arr:
        if type(element) is int and element > 0:
            return sum(arr)
        elif element not in arr:
            return 0
        else:
            return 0
print(positive_sum([-1,2,3,4,-5]), 'primul ex, 9 trebuie')
print(positive_sum([1,2,3,4,5]), 'doilea ex , 15 trebuie')
print(positive_sum([1,-2,3,4,5]), 'treilea ex, trebuie 13 ')


# Given an array of integers.
#
# Return an array, where the first element is the count of positives numbers and the second element is sum of negative
# numbers. 0 is neither positive nor negative.
#
# If the input is an empty array or is null, return an empty array.
#
# Example
# For input [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, -11, -12, -13, -14, -15], you should return [10, -65].

def count_positives_sum_negatives(arr):
    poz_arr = 0                         # punem 0 pentru ca de la 0 incep numerele (apoi va urma 1 pt ca linia 384)
    neg_arr = 0

    for x in arr:                       # pentru fiecare element din arr
        if x > 0:
            poz_arr += 1                # += 1 pentru ca sunt numere pozitive
        elif x < 0:
            neg_arr += x                # += x pentru ca sunt negative
        return [poz_arr, neg_arr]

    if arr is None or len(arr) == 0:     #daca arr este null sau empty ( is null = arr id None) is empty ( len(arr)==0
        return []                        # return [] pt ca trebuie sa returneze un empty array

print(count_positives_sum_negatives([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, -11, -12, -13, -14, -15]),[10,-65] , 'aici ')


def positive_sum(arr):
    newarr = 0
    for num in arr:
        if num > 0:
            newarr += num
            return newarr
print(positive_sum([1,-2,3,4,5]), 'ifnijhr \n')


# Complete the function that accepts a string parameter, and reverses each word in the string. All spaces in the
# string should be retained.

# "This is an example!" ==> "sihT si na !elpmaxe"
# "double  spaces"      ==> "elbuod  secaps"

def reverse_words(text):
    """ functie care inverseaza fiecare cuvant dintr-un string - propozitie si pastreaza spatiile """
    textRev = ''
    lista = text.split(' ')    # Metoda .split() sparge un string in elemente distincte pe care le introduce intr-o lista
                            # si le separa dupa ' ' (spatiu)
                            # daca avem parametru x .split(x), este folosit pentru a sparge string-ul la gasirea lui x
    for cuvant in lista:
        lci = list(cuvant)  # spargem cuvantul in lista ca sa inversam ordinea lieterelor din cuvant
        lci.reverse()         # .reverse() este metoda care modifica structura liste initiale la apelare
        ci = "".join(lci)   # unim elementele din lista inapoi in string
        textRev += ci + ' '
    return textRev[:-1]


print(reverse_words('This is an example!'))
print(reverse_words('double  spaces'))


# Simple, given a string of words, return the length of the shortest word(s).
#
# String will never be empty and you do not need to account for different data types.

def find_short(s):
    """ de gasit cel mai scurt cuvant dintr-o propozitie """

    lista = s.split()

    listalen = []

    for cuvant in lista:
        listalen.append(len(cuvant))

    return min(listalen)

print(find_short('bitcoin take over the world maybe who knows perhaps'))


# 15.01.2024 - Gabriel

#   Your task is to create a function that does four basic mathematical operations.
#
# The function should take three arguments - operation(string/char), value1(number), value2(number).
# The function should return result of numbers after applying the chosen operation.
def basic_op(operator, value1, value2):

    # metoda compacta
    return eval(str(value1) + operator + str(value2))

print(basic_op('+', 4, 7))

# Info pentru functia eval(expresie string) - https://www.programiz.com/python-programming/methods/built-in/eval


# Alex B

# Implement the function unique_in_order which takes as argument a sequence and returns a list of items without any elements with the same value next to each other and preserving the original order of elements.

def unique_in_order(sequence):

  order = []

  if not sequence:
    return order

  order.append(sequence[0])
  for i in range(1,len(sequence)):
    if sequence[i-1] != sequence[i]:
      order.append(sequence[i])
  return order

print(unique_in_order('AAAABBBCCDAABBB'))

# Continuarea exercitiilor de pe codewars - Gabriel, 7-8 Kyu 14.02.2024

# Create a function which answers the question "Are you playing banjo?".
# If your name starts with the letter "R" or lower case "r", you are playing banjo!
#
# The function takes a name as its only argument, and returns one of the following strings:
#
# name + " plays banjo"
# name + " does not play banjo"
# Names given are always valid strings.

def playing_banjo(name):
    if name[0].lower() == 'r':
        return f'{name} plays banjo'
    return f'{name} does not play banjo'

print(playing_banjo('aul'), '\n')


# The Western Suburbs Croquet Club has two categories of membership, Senior and Open. They would like your help with an application form that will tell prospective members which category they will be placed.
#
# To be a senior, a member must be at least 55 years old and have a handicap greater than 7. In this croquet club, handicaps range from -2 to +26; the better the player the lower the handicap.
#
# Input
# Input will consist of a list of pairs. Each pair contains information for a single potential member. Information consists of an integer for the person's age and an integer for the person's handicap.
#
# Output
# Output will consist of a list of string values (in Haskell and C: Open or Senior) stating whether the respective member is to be placed in the senior or open category.
#
# Example
# input =  [[18, 20], [45, 2], [61, 12], [37, 6], [21, 21], [78, 9]]
# output = ["Open", "Open", "Senior", "Open", "Open", "Senior"]

def open_or_senior(data):
    result_data = []
    for lista in data:
        if lista[0] >= 55 and lista[1] > 7:
            result_data.append('Senior')
        else:
            result_data.append('Open')
    return result_data

print(open_or_senior([[18, 20], [45, 2], [61, 12], [37, 6], [21, 21], [78, 9]]), '\n')


# Can you find the needle in the haystack?
#
# Write a function findNeedle() that takes an array full of junk but containing one "needle"
#
# After your function finds the needle it should return a message (as a string) that says:
#
# "found the needle at position " plus the index it found the needle, so:
#
# Example(Input --> Output)
#
# ["hay", "junk", "hay", "hay", "moreJunk", "needle", "randomJunk"] --> "found the needle at position 5"

def find_needle(haystack):
    return f'found the needle at position {haystack.index('needle')}'

print(find_needle(["hay", "junk", "hay", "hay", "moreJunk", "needle", "randomJunk"]), '\n')


# Write a function to convert a name into initials. This kata strictly takes two words with one space in between them.
#
# The output should be two capital letters with a dot separating them.
#
# It should look like this:
#
# Sam Harris => S.H
#
# patrick feeney => P.F

def abbrev_name(name):
    # Prima data convertim stringul in lista cu metoda split, pentru a separa stringul in doua elemente dupa spatiu
    lista = name.split()
    return f'{lista[0][0].upper()}.{lista[1][0].upper()}'

print(abbrev_name('patrick feeney'), '\n')


# In this kata you will create a function that takes a list of non-negative integers and strings and returns a new list with the strings filtered out.
#
# Example
# filter_list([1,2,'a','b']) == [1,2]
# filter_list([1,'a','b',0,15]) == [1,0,15]
# filter_list([1,2,'aasf','1','123',123]) == [1,2,123]

def filter_list(l):
    """return a new list with the strings filtered out"""
    l2 = []
    for elem in l:
        if type(elem) == int:
            l2.append(elem)

    return l2

print(filter_list([1,2,'aasf','1','123',123]), '\n')


# Create a function with two arguments that will return an array of the first n multiples of x.
#
# Assume both the given number and the number of times to count will be positive numbers greater than 0.
#
# Return the results as an array or list ( depending on language ).
#
# Examples
# count_by(1,10) #should return [1,2,3,4,5,6,7,8,9,10]
# count_by(2,5) #should return [2,4,6,8,10]

def count_by(x, n):
    """
    Return a sequence of numbers counting by `x` `n` times.
    """
    x_init = x
    l = []
    for i in range(n):
        l.append(x)
        x += x_init

    return l

print(count_by(2, 5), '\n')
print(count_by(1, 10), '\n')

def count_by2(x, n):
    l = []
    for i in range(1, n+1):
        l.append(x * i)

    return l

print(count_by2(2, 6), '\n')



# Deoxyribonucleic acid (DNA) is a chemical found in the nucleus of cells and carries the "instructions" for the development and functioning of living organisms.
#
# If you want to know more: http://en.wikipedia.org/wiki/DNA
#
# In DNA strings, symbols "A" and "T" are complements of each other, as "C" and "G". Your function receives one side of the DNA (string, except for Haskell); you need to return the other complementary side. DNA strand is never empty or there is no DNA at all (again, except for Haskell).
#
# More similar exercise are found here: http://rosalind.info/problems/list-view/ (source)
#
# Example: (input --> output)
#
# "ATTGC" --> "TAACG"
# "GTAT" --> "CATA"

def DNA_strand(dna):
    # code here
    dna2 = ''
    for litera in dna:
        if litera == 'A':
            dna2 += 'T'
        elif litera == 'T':
            dna2 += 'A'
        elif litera == 'C':
            dna2 += 'G'
        else:
            dna2 += 'C'
    return dna2

print(DNA_strand('ATTGC'), '\n')


def DNA_strand2(dna):
    dict = {
        'A': 'T',
        'T': 'A',
        'C': 'G',
        'G': 'C'
    }

    dna2 = ''

    for litera in dna:
        dna2 += dict[litera]

    return dna2

print(DNA_strand2('GTAT'), '\n')



# Create a function that returns the sum of the two lowest positive numbers given an array of minimum 4 positive integers. No floats or non-positive integers will be passed.
#
# For example, when an array is passed like [19, 5, 42, 2, 77], the output should be 7.
#
# [10, 343445353, 3453445, 3453545353453] should return 3453455.

def sum_two_smallest_numbers(numbers):
    #your code here
    return sum(sorted(numbers)[:2])
    # listele numerice se sorteaza cu functia sorted([n, m, x, y, z])

print(sum_two_smallest_numbers([19, 5, 42, 2, 77]), '\n')


# Task:
# Given a non-negative integer, 3 for example, return a string with a murmur: "1 sheep...2 sheep...3 sheep...".
# Input will always be valid, i.e. no negative integers.

def count_sheep(n):
    # your code
    s = ''
    for i in range(1, n+1):
        s += f'{i} sheep...'
    return s

print(count_sheep(10), '\n')


# You are going to be given a word. Your job is to return the middle character of the word. If the word's length is odd, return the middle character. If the word's length is even, return the middle 2 characters.
#
# #Examples:
#
# Kata.getMiddle("test") should return "es"
#
# Kata.getMiddle("testing") should return "t"
#
# Kata.getMiddle("middle") should return "dd"
#
# Kata.getMiddle("A") should return "A"
# #Input
#
# A word (string) of length 0 < str < 1000 (In javascript you may get slightly more than 1000 in some test cases due to an error in the test cases). You do not need to test for this. This is only here to tell you that you do not need to worry about your solution timing out.
#
# #Output
#
# The middle character(s) of the word represented as a string.

def get_middle(s):
    if len(s) <= 2:
        return s
    else:
        if len(s) % 2:
            # Situatia lungimii impare
            return s[len(s) // 2]
        else:
            # Lungimea para
            return s[int(len(s) / 2) - 1 : int(len(s) / 2) + 1]

print(get_middle('A'))


def get_middle2(s):
    index, odd = divmod(len(s), 2)
    if odd:
        return s[index]
    return s[index - 1 : index + 1]


print(get_middle2('testing'), '\n')
print(get_middle2('middle'), '\n')
print(7 % 2, 7 // 2,'restul si catul lui 7 impartit la 2\n')


# Given a string of digits, you should replace any digit below 5 with '0' and any digit 5 and above with '1'.
# Return the resulting string.
#
# Note: input will never be an empty string: "45385593107843568" -> "01011110001100111"

def fake_bin(x):
    s = ''
    for n in x:
        if n < '5':
            s += '0'
        else:
            s += '1'

    return s

print(fake_bin('45385593107843568'), '\n')


# Our football team has finished the championship.
#
# Our team's match results are recorded in a collection of strings. Each match is represented by a string in the format "x:y", where x is our team's score and y is our opponents score.
#
# For example: ["3:1", "2:2", "0:1", ...]
#
# Points are awarded for each match as follows:
#
# if x > y: 3 points (win)
# if x < y: 0 points (loss)
# if x = y: 1 point (tie)
# We need to write a function that takes this collection and returns the number of points our team (x) got in the championship by the rules given above.
#
# Notes:
#
# our team always plays 10 matches in the championship
# 0 <= x <= 4
# 0 <= y <= 4

def points(games):
    puncte = 0

    for punctaj in games:
        if punctaj[0] > punctaj[2]:
            puncte += 3
        elif punctaj[0] == punctaj[2]:
            puncte += 1

    return puncte


print(points(['1:0', '2:0' , '3:0', '4:0', '2:1', '3:1', '4:1', '3:2', '4:2', '4:3']), '\n')


# Given a month as an integer from 1 to 12, return to which quarter of the year it belongs as an integer number.
#
# For example: month 2 (February), is part of the first quarter; month 6 (June), is part of the second quarter;
# and month 11 (November), is part of the fourth quarter.
#
# Constraint:
#
# 1 <= month <= 12


def quarter_of(month):
    # your code here
    if month < 4:
        return 1
    elif month < 7:
        return 2
    elif month < 10:
        return 3
    return 4

print(quarter_of(5), '\n')

def quarter_of2(month):
    return (month + 2) // 3

print(quarter_of2(5), '\n')

def quarter_of3(month):
    year ={1: [1, 2, 3], 2: [4, 5, 6], 3: [7, 8, 9], 4: [10, 11, 12]}
    for k, v in year.items():
        if month in v:
            return k

print(quarter_of3(5), '\n')


# Convert number to reversed array of digits
# Given a random non-negative number, you have to return the digits of this number within an array in reverse order.
#
# Example(Input => Output):
# 35231 => [1,3,2,5,3]
# 0 => [0]

def digitize(n):
    l = []
    for m in str(n):
        l.append(int(m))
    l.reverse()     # metoda [].reverse este pentru liste, iar functia reversed('text') este pentru stringuri
    return l

print(digitize(35231), '\n')

lista1 = [1, 2, 5, 8]
lista1.reverse()
print(lista1)
print([1, 2, 4, 7, 5].pop())

# Presupunem ca nu exista functia reverse()

def digitize2(n):
    l = []
    inx = len(str(n))
    while inx > 0:
        inx -= 1
        l.append(int(str(n)[inx]))

    return l

print(digitize2(35231))

print('textdirect', list(reversed('textdirect')), '\n')

def digitize3(n):
    return [int(m) for m in list(reversed(str(n)))]

print(digitize3(35231))

def digitize4(n):
    l = list(reversed(str(n)))
    l2 = []
    for m in l:
        l2.append(int(m))
    return l2

print(digitize4(35231))

lista2 = [2, 3, 4, 7, 9]

print([n ** 2 for n in lista2])
print(list(map(str, lista2)))  # functia map are doi parametri map(x, y) unde x e o functie, iar y e un iterabil (lista sau string)


""" Exercitii de pe codewars dictutate in clasa """

# 12.01.2024

# Liviu

def to_alternating_case(string):
    """ Transformarea literelor mici in litere mari si viceversa dintr-un string """

    stringAlternat = ""
    for litera in string:
        if litera.islower():
            stringAlternat += litera.upper()
        else:
            stringAlternat += litera.lower()
    return stringAlternat

print(to_alternating_case('HeLLo WoRLD'))

# A doua versiune a acestui exercitiu

def to_altenrating_case2(string):

    stringAlt = ''

    # iteram listaString cu for bucla
    for ind in range(len(string)):
        if string[ind].islower():
            stringAlt += string[ind].upper()
        else:
            stringAlt += string[ind].lower()

    return stringAlt

print(to_altenrating_case2('HeLLo WoRLD'))

# Eliminarea vocalelor mici aeiou


def shortcut(s):
    """ de eliminat vocalele mici aeiou """
    s2 = ''
    ref = 'aeiou'

    for litera in s:
        if litera not in ref:
            s2 += litera

    return s2

print(shortcut("HELLO"))

# Dublarea caracterelor intr-un string

def repeat_characters(input_string):
  return "".join([char * 2 for char in input_string])


def repeat_characters2(in_str):
  str = ''
  for litera in in_str:
      str += litera * 2
  return(str)



#def repeat_characters3(input_string):


# Complete the function that accepts a string parameter, and reverses each word in the string. All spaces in the
# string should be retained.

# "This is an example!" ==> "sihT si na !elpmaxe"
# "double  spaces"      ==> "elbuod  secaps"

def reverse_words(text):
    """ functie care inverseaza fiecare cuvant dintr-un string - propozitie si pastreaza spatiile """
    textRev = ''
    lista = text.split(' ')    # Metoda .split() sparge un string in elemente distincte pe care le introduce intr-o lista
                            # si le separa dupa ' ' (spatiu)
                            # daca avem parametru x .split(x), este folosit pentru a sparge string-ul la gairea lui x
    for cuvant in lista:
        lci = list(cuvant)  # spargem cuvantul in lista ca sa inversam ordinea lieterelor din cuvant
        lci.reverse()         # .reverse() este metoda care modifica structura liste initiale la apelare
        ci = "".join(lci)   # unim elementele din lista inapoi in string
        textRev += ci + ' '
    return textRev[:-1]


print(reverse_words('This is an example!'))
print(reverse_words('double  spaces'))


# Simple, given a string of words, return the length of the shortest word(s).
#
# String will never be empty and you do not need to account for different data types.

def find_short(s):
    """ de gasit cel mai scurt cuvant dintr-o propozitie """

    lista = s.split()

    listalen = []

    for cuvant in lista:
        listalen.append(len(cuvant))

    return min(listalen)

print(find_short('bitcoin take over the world maybe who knows perhaps'))


# 15.01.2024 - Gabriel

#   Your task is to create a function that does four basic mathematical operations.
#
# The function should take three arguments - operation(string/char), value1(number), value2(number).
# The function should return result of numbers after applying the chosen operation.
def basic_op(operator, value1, value2):

    # metoda compacta
    return eval(str(value1) + operator + str(value2))

print(basic_op('+', 4, 7))

# Info pentru functia eval(expresie string) - https://www.programiz.com/python-programming/methods/built-in/eval


# Alex B

# Implement the function unique_in_order which takes as argument a sequence and returns a list of items without any elements with the same value next to each other and preserving the original order of elements.

def unique_in_order(sequence):

  order = []

  if not sequence:
    return order

  order.append(sequence[0])
  for i in range(1,len(sequence)):
    if sequence[i-1] != sequence[i]:
      order.append(sequence[i])
  return order

print(unique_in_order('AAAABBBCCDAABBB'))


# Build a function that returns an array of integers from n to 1 where n>0.
# Example : n=5 --> [5,4,3,2,1]


def reverse_seq(n):
    lista = list(range(1, n + 1))     # creem un iterabil cu functia range cu valori de la 1 la n + 1 ca sa il includa
    # si pe n, dupa pasam acest iterabil in functia list ca sa stocam valorile produse de functia range in lista.
    lista.reverse()                   # apelam metoda .reverse() pe lista metoda care modifica forma listei inversand
    #ordinea elementelor din lista.
    return lista

print(reverse_seq(5))

# Given a non-empty array of integers, return the result of multiplying the values together in order. Example:
# [1, 2, 3, 4] => 1 * 2 * 3 * 4 = 24

def grow(arr):
    prod = 1                 # am  declarat o variabila, pt ca de la 1 incepem (orice nr inmultit cu 0 este 0)
    #daca puneam prod dupa for nu mai trecea de unu(pt ca bucla o ia si se reseta pe prob la 1 la fiecare iteratie)
    for n in arr:
        #prod = 1           #daca  il  bag aici mi-l blocheaza la 1 ! !!!! deci nu aici!!!!
        print(prod)      #
        prod *= n
    return prod

print(grow( [2, 2, 2, 2, 2, 2]))

# Summation
# Write a program that finds the summation of every number from 1 to num. The number will always be a positive integer
# greater than 0. Your function only needs to return the result, what is shown between parentheses in the example below
# is how you reach that result and it's not part of it, see the sample tests.
# For example (Input -> Output):
# 2 -> 3 (1 + 2)
# 8 -> 36 (1 + 2 + 3 + 4 + 5 + 6 + 7 + 8)

def summation(num):                                             #varianta lunga la sum()
    abcd = list(range(1, num + 1))
    adunari = 0     #aici scriem de lace nr incepe!!!
    for n in abcd:
        adunari += n # pe rand va lua fiecare n!!!!
    return adunari   #returnam ceea ce am dat ,,crestere''


print(summation(6))


def summation2(num):
    abcd = list(range(1, num + 1))
    return sum(abcd)                       # functia sum calculeaza suma elementelor numerice dintr- un array similar
#cu metoda for de la linia 188!


# Create a function that accepts a string and a single character, and returns an integer of the count of occurrences
# the 2nd argument is found in the first one.
# If no occurrences can be found, a count of 0 should be returned.
# ("Hello", "o")  ==>  1
# ("Hello", "l")  ==>  2
# ("", "z")       ==>  0
# str_count("Hello", 'o'); // returns 1
# str_count("Hello", 'l'); // returns 2
# str_count("", 'z'); // returns 0
# Notes
# The first argument can be an empty string
# In languages with no distinct character data type, the second argument will be a string of length 1


def str_count(strng, letter):
    aparitii = 0            # am creeat variabila aparitie ca sa  stocam numarul aparitiilor letter in strng
    for litera in strng:    # am interat fiecare litera in strng
        if litera == letter:  # am comparat daca litera egala cu letter
            aparitii += 1    # am incrementat variabila aparitii cu valoarea 1

    return aparitii         #am returnat aparitiile (unde s -au stocat)


print(str_count('hello', 'l'))


# The Story:
# Bob is working as a bus driver. However, he has become extremely popular amongst the city's residents.
# With so many passengers wanting to get aboard his bus, he sometimes has to face the problem of not enough space left
# on the bus! He wants you to write a simple program telling him if he will be able to fit all the passengers.
# Task Overview:
# You have to write a function that accepts three parameters:
# cap is the amount of people the bus can hold excluding the driver.
# on is the number of people on the bus excluding the driver.
# wait is the number of people waiting to get on to the bus excluding the driver.
# If there is enough space, return 0, and if there isn't, return the number of passengers he can't take.
# Usage Examples:
# cap = 10, on = 5, wait = 5 --> 0 # He can fit all 5 passengers
# cap = 100, on = 60, wait = 50 --> 10 # He can't fit 10 of the 50 waiting


def enough(cap, on, wait):
    loc_liber = cap - on         # am creat variabila loc liber in care am stocat diferenta dintre capacitatea
    # autobuzului si locurile ocupate
    if loc_liber >= wait:        # am pus conditia ca locurile libere sa fie mai mare sau egale cu pers care asteapta
        #in statie (wait)
        return 0                 # am returnat 0 pt ca locurile libere sunt mai mare sau egale cu wait
    else:
        return wait - loc_liber  #am facut diferenta dintre pers care ast(wait) si locurile libere ca sa aflam
    #cati oameni raman in statie

print(enough(100 , 60 , 50))


# Task:
# Your task is to write a function which returns the sum of following series upto nth term(parameter).
# Series: 1 + 1/4 + 1/7 + 1/10 + 1/13 + 1/16 +...
# Rules:
# You need to round the answer to 2 decimal places and return it as String.
#
# If the given value is 0 then it should return 0.00
#
# You will only be given Natural Numbers as arguments.
#
# Examples:(Input --> Output)
# 1 --> 1 --> "1.00"
# 2 --> 1 + 1/4 --> "1.25"
# 5 --> 1 + 1/4 + 1/7 + 1/10 + 1/13 --> "1.57"


def series_sum(n):
    numar = 1           # declaram variabila numar cu valoarea 1, care va asigura incrementarea cu valoarea 3
                        # a divizorului
    numartot = 0        # Variabila numartot va stoca adunarile operatiilor in functie de numarul n - operatii egale cu
                        # numarul n
    if n == 1:          # Eliminam situatia cand n = 1, ca sa putem returna un string cu doua zero dupa unu
        return '1.00'
    elif n == 0:
        return '0.00'
    for i in range(n):      #i = nr de iteratii - cream o bucla for cu parametru n - n iteratii ale buclei
        numartot += 1 / numar   # stocam in numartot rezultatul operatiei de impartire a lui 1 la numar
        numar += 3              # incrementam cu 3 valoarea lui numar pentru a respecta conditia operatiilor

    strnum = str(round(numartot, 2))

    if len(strnum) == 3:
        strnum += '0'

    return strnum  # rotunjim la doua zecimale numartot si dupa il transformam in string conform
                                    # cerintelor problemei

print(series_sum(500))


i = 0
while i <= 5:
    i += 1
    print(i)

# Write a function to split a string and convert it into an array of words.
#  Examples (Input ==> Output):
# "Robin Singh" ==> ["Robin", "Singh"]
#  "I love arrays they are my favorite" ==> ["I", "love", "arrays", "they", "are", "my", "favorite"]

def string_to_array(s):
    return list(s.split(" "))

#am dat return list si am cautat pe google sintaxa de split


# Complete the function that accepts a string parameter, and reverses each word in the string. All spaces in the
# string should be retained.

# "This is an example!" ==> "sihT si na !elpmaxe"
# "double  spaces"      ==> "elbuod  secaps"

def reverse_words(text):
    """ functie care inverseaza fiecare cuvant dintr-un string - propozitie si pastreaza spatiile """
    textRev = ''
    lista = text.split(' ')    # Metoda .split() sparge un string in elemente distincte pe care le introduce intr-o lista
                            # si le separa dupa ' ' (spatiu)
                            # daca avem parametru x .split(x), este folosit pentru a sparge string-ul la gairea lui x
    for cuvant in lista:
        lci = list(cuvant)  # spargem cuvantul in lista ca sa inversam ordinea lieterelor din cuvant
        lci.reverse()         # .reverse() este metoda care modifica structura liste initiale la apelare
        ci = "".join(lci)   # unim elementele din lista inapoi in string
        textRev += ci + ' '
    return textRev[:-1]


print(reverse_words('This is an example!'))
print(reverse_words('double  spaces'))


# Simple, given a string of words, return the length of the shortest word(s).
#
# String will never be empty and you do not need to account for different data types.

def find_short(s):
    """ de gasit cel mai scurt cuvant dintr-o propozitie """

    lista = s.split()

    listalen = []

    for cuvant in lista:
        listalen.append(len(cuvant))

    return min(listalen)

print(find_short('bitcoin take over the world maybe who knows perhaps'))


def positive_sum(arr):
    for element in arr:
        if type(element) is int and element > 0:
            return sum(arr)
        elif element not in arr:
            return 0
        else:
            return 0
print(positive_sum([-1,2,3,4,-5]), 'primul ex, 9 trebuie')
print(positive_sum([1,2,3,4,5]), 'doilea ex , 15 trebuie')
print(positive_sum([1,-2,3,4,5]), 'treilea ex, trebuie 13 ')


# Given an array of integers.
#
# Return an array, where the first element is the count of positives numbers and the second element is sum of negative
# numbers. 0 is neither positive nor negative.
#
# If the input is an empty array or is null, return an empty array.
#
# Example
# For input [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, -11, -12, -13, -14, -15], you should return [10, -65].

def count_positives_sum_negatives(arr):
    poz_arr = 0                         # punem 0 pentru ca de la 0 incep numerele (apoi va urma 1 pt ca linia 384)
    neg_arr = 0

    for x in arr:                       # pentru fiecare element din arr
        if x > 0:
            poz_arr += 1                # += 1 pentru ca sunt numere pozitive
        elif x < 0:
            neg_arr += x                # += x pentru ca sunt negative
        return [poz_arr, neg_arr]

    if arr is None or len(arr) == 0:     #daca arr este null sau empty ( is null = arr id None) is empty ( len(arr)==0
        return []                        # return [] pt ca trebuie sa returneze un empty array

print(count_positives_sum_negatives([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, -11, -12, -13, -14, -15]),[10,-65] , 'aici ')


def positive_sum(arr):
    newarr = 0
    for num in arr:
        if num > 0:
            newarr += num
            return newarr
print(positive_sum([1,-2,3,4,5]), 'ifnijhr \n')


# Complete the function that accepts a string parameter, and reverses each word in the string. All spaces in the
# string should be retained.

# "This is an example!" ==> "sihT si na !elpmaxe"
# "double  spaces"      ==> "elbuod  secaps"

def reverse_words(text):
    """ functie care inverseaza fiecare cuvant dintr-un string - propozitie si pastreaza spatiile """
    textRev = ''
    lista = text.split(' ')    # Metoda .split() sparge un string in elemente distincte pe care le introduce intr-o lista
                            # si le separa dupa ' ' (spatiu)
                            # daca avem parametru x .split(x), este folosit pentru a sparge string-ul la gasirea lui x
    for cuvant in lista:
        lci = list(cuvant)  # spargem cuvantul in lista ca sa inversam ordinea lieterelor din cuvant
        lci.reverse()         # .reverse() este metoda care modifica structura liste initiale la apelare
        ci = "".join(lci)   # unim elementele din lista inapoi in string
        textRev += ci + ' '
    return textRev[:-1]


print(reverse_words('This is an example!'))
print(reverse_words('double  spaces'))


# Simple, given a string of words, return the length of the shortest word(s).
#
# String will never be empty and you do not need to account for different data types.

def find_short(s):
    """ de gasit cel mai scurt cuvant dintr-o propozitie """

    lista = s.split()

    listalen = []

    for cuvant in lista:
        listalen.append(len(cuvant))

    return min(listalen)

print(find_short('bitcoin take over the world maybe who knows perhaps'))


# 15.01.2024 - Gabriel

#   Your task is to create a function that does four basic mathematical operations.
#
# The function should take three arguments - operation(string/char), value1(number), value2(number).
# The function should return result of numbers after applying the chosen operation.
def basic_op(operator, value1, value2):

    # metoda compacta
    return eval(str(value1) + operator + str(value2))

print(basic_op('+', 4, 7))

# Info pentru functia eval(expresie string) - https://www.programiz.com/python-programming/methods/built-in/eval


# Alex B

# Implement the function unique_in_order which takes as argument a sequence and returns a list of items without any elements with the same value next to each other and preserving the original order of elements.

def unique_in_order(sequence):

  order = []

  if not sequence:
    return order

  order.append(sequence[0])
  for i in range(1,len(sequence)):
    if sequence[i-1] != sequence[i]:
      order.append(sequence[i])
  return order

print(unique_in_order('AAAABBBCCDAABBB'))

# Continuarea exercitiilor de pe codewars - Gabriel, 7-8 Kyu 14.02.2024

# Create a function which answers the question "Are you playing banjo?".
# If your name starts with the letter "R" or lower case "r", you are playing banjo!
#
# The function takes a name as its only argument, and returns one of the following strings:
#
# name + " plays banjo"
# name + " does not play banjo"
# Names given are always valid strings.

def playing_banjo(name):
    if name[0].lower() == 'r':
        return f'{name} plays banjo'
    return f'{name} does not play banjo'

print(playing_banjo('aul'), '\n')


# The Western Suburbs Croquet Club has two categories of membership, Senior and Open. They would like your help with an application form that will tell prospective members which category they will be placed.
#
# To be a senior, a member must be at least 55 years old and have a handicap greater than 7. In this croquet club, handicaps range from -2 to +26; the better the player the lower the handicap.
#
# Input
# Input will consist of a list of pairs. Each pair contains information for a single potential member. Information consists of an integer for the person's age and an integer for the person's handicap.
#
# Output
# Output will consist of a list of string values (in Haskell and C: Open or Senior) stating whether the respective member is to be placed in the senior or open category.
#
# Example
# input =  [[18, 20], [45, 2], [61, 12], [37, 6], [21, 21], [78, 9]]
# output = ["Open", "Open", "Senior", "Open", "Open", "Senior"]

def open_or_senior(data):
    result_data = []
    for lista in data:
        if lista[0] >= 55 and lista[1] > 7:
            result_data.append('Senior')
        else:
            result_data.append('Open')
    return result_data

print(open_or_senior([[18, 20], [45, 2], [61, 12], [37, 6], [21, 21], [78, 9]]), '\n')


# Can you find the needle in the haystack?
#
# Write a function findNeedle() that takes an array full of junk but containing one "needle"
#
# After your function finds the needle it should return a message (as a string) that says:
#
# "found the needle at position " plus the index it found the needle, so:
#
# Example(Input --> Output)
#
# ["hay", "junk", "hay", "hay", "moreJunk", "needle", "randomJunk"] --> "found the needle at position 5"

def find_needle(haystack):
    return f'found the needle at position {haystack.index('needle')}'

print(find_needle(["hay", "junk", "hay", "hay", "moreJunk", "needle", "randomJunk"]), '\n')


# Write a function to convert a name into initials. This kata strictly takes two words with one space in between them.
#
# The output should be two capital letters with a dot separating them.
#
# It should look like this:
#
# Sam Harris => S.H
#
# patrick feeney => P.F

def abbrev_name(name):
    # Prima data convertim stringul in lista cu metoda split, pentru a separa stringul in doua elemente dupa spatiu
    lista = name.split()
    return f'{lista[0][0].upper()}.{lista[1][0].upper()}'

print(abbrev_name('patrick feeney'), '\n')


# In this kata you will create a function that takes a list of non-negative integers and strings and returns a new list with the strings filtered out.
#
# Example
# filter_list([1,2,'a','b']) == [1,2]
# filter_list([1,'a','b',0,15]) == [1,0,15]
# filter_list([1,2,'aasf','1','123',123]) == [1,2,123]

def filter_list(l):
    """return a new list with the strings filtered out"""
    l2 = []
    for elem in l:
        if type(elem) == int:
            l2.append(elem)

    return l2

print(filter_list([1,2,'aasf','1','123',123]), '\n')


# Create a function with two arguments that will return an array of the first n multiples of x.
#
# Assume both the given number and the number of times to count will be positive numbers greater than 0.
#
# Return the results as an array or list ( depending on language ).
#
# Examples
# count_by(1,10) #should return [1,2,3,4,5,6,7,8,9,10]
# count_by(2,5) #should return [2,4,6,8,10]

def count_by(x, n):
    """
    Return a sequence of numbers counting by `x` `n` times.
    """
    x_init = x
    l = []
    for i in range(n):
        l.append(x)
        x += x_init

    return l

print(count_by(2, 5), '\n')
print(count_by(1, 10), '\n')

def count_by2(x, n):
    l = []
    for i in range(1, n+1):
        l.append(x * i)

    return l

print(count_by2(2, 6), '\n')



# Deoxyribonucleic acid (DNA) is a chemical found in the nucleus of cells and carries the "instructions" for the development and functioning of living organisms.
#
# If you want to know more: http://en.wikipedia.org/wiki/DNA
#
# In DNA strings, symbols "A" and "T" are complements of each other, as "C" and "G". Your function receives one side of the DNA (string, except for Haskell); you need to return the other complementary side. DNA strand is never empty or there is no DNA at all (again, except for Haskell).
#
# More similar exercise are found here: http://rosalind.info/problems/list-view/ (source)
#
# Example: (input --> output)
#
# "ATTGC" --> "TAACG"
# "GTAT" --> "CATA"

def DNA_strand(dna):
    # code here
    dna2 = ''
    for litera in dna:
        if litera == 'A':
            dna2 += 'T'
        elif litera == 'T':
            dna2 += 'A'
        elif litera == 'C':
            dna2 += 'G'
        else:
            dna2 += 'C'
    return dna2

print(DNA_strand('ATTGC'), '\n')


def DNA_strand2(dna):
    dict = {
        'A': 'T',
        'T': 'A',
        'C': 'G',
        'G': 'C'
    }

    dna2 = ''

    for litera in dna:
        dna2 += dict[litera]

    return dna2

print(DNA_strand2('GTAT'), '\n')



# Create a function that returns the sum of the two lowest positive numbers given an array of minimum 4 positive integers. No floats or non-positive integers will be passed.
#
# For example, when an array is passed like [19, 5, 42, 2, 77], the output should be 7.
#
# [10, 343445353, 3453445, 3453545353453] should return 3453455.

def sum_two_smallest_numbers(numbers):
    #your code here
    return sum(sorted(numbers)[:2])
    # listele numerice se sorteaza cu functia sorted([n, m, x, y, z])

print(sum_two_smallest_numbers([19, 5, 42, 2, 77]), '\n')


# Task:
# Given a non-negative integer, 3 for example, return a string with a murmur: "1 sheep...2 sheep...3 sheep...".
# Input will always be valid, i.e. no negative integers.

def count_sheep(n):
    # your code
    s = ''
    for i in range(1, n+1):
        s += f'{i} sheep...'
    return s

print(count_sheep(10), '\n')


# You are going to be given a word. Your job is to return the middle character of the word. If the word's length is odd, return the middle character. If the word's length is even, return the middle 2 characters.
#
# #Examples:
#
# Kata.getMiddle("test") should return "es"
#
# Kata.getMiddle("testing") should return "t"
#
# Kata.getMiddle("middle") should return "dd"
#
# Kata.getMiddle("A") should return "A"
# #Input
#
# A word (string) of length 0 < str < 1000 (In javascript you may get slightly more than 1000 in some test cases due to an error in the test cases). You do not need to test for this. This is only here to tell you that you do not need to worry about your solution timing out.
#
# #Output
#
# The middle character(s) of the word represented as a string.

def get_middle(s):
    if len(s) <= 2:
        return s
    else:
        if len(s) % 2:
            # Situatia lungimii impare
            return s[len(s) // 2]
        else:
            # Lungimea para
            return s[int(len(s) / 2) - 1 : int(len(s) / 2) + 1]

print(get_middle('A'))


def get_middle2(s):
    index, odd = divmod(len(s), 2)
    if odd:
        return s[index]
    return s[index - 1 : index + 1]


print(get_middle2('testing'), '\n')
print(get_middle2('middle'), '\n')
print(7 % 2, 7 // 2,'restul si catul lui 7 impartit la 2\n')


# Given a string of digits, you should replace any digit below 5 with '0' and any digit 5 and above with '1'.
# Return the resulting string.
#
# Note: input will never be an empty string: "45385593107843568" -> "01011110001100111"

def fake_bin(x):
    s = ''
    for n in x:
        if n < '5':
            s += '0'
        else:
            s += '1'

    return s

print(fake_bin('45385593107843568'), '\n')


# Our football team has finished the championship.
#
# Our team's match results are recorded in a collection of strings. Each match is represented by a string in the format "x:y", where x is our team's score and y is our opponents score.
#
# For example: ["3:1", "2:2", "0:1", ...]
#
# Points are awarded for each match as follows:
#
# if x > y: 3 points (win)
# if x < y: 0 points (loss)
# if x = y: 1 point (tie)
# We need to write a function that takes this collection and returns the number of points our team (x) got in the championship by the rules given above.
#
# Notes:
#
# our team always plays 10 matches in the championship
# 0 <= x <= 4
# 0 <= y <= 4

def points(games):
    puncte = 0

    for punctaj in games:
        if punctaj[0] > punctaj[2]:
            puncte += 3
        elif punctaj[0] == punctaj[2]:
            puncte += 1

    return puncte


print(points(['1:0', '2:0' , '3:0', '4:0', '2:1', '3:1', '4:1', '3:2', '4:2', '4:3']), '\n')


# Given a month as an integer from 1 to 12, return to which quarter of the year it belongs as an integer number.
#
# For example: month 2 (February), is part of the first quarter; month 6 (June), is part of the second quarter;
# and month 11 (November), is part of the fourth quarter.
#
# Constraint:
#
# 1 <= month <= 12


def quarter_of(month):
    # your code here
    if month < 4:
        return 1
    elif month < 7:
        return 2
    elif month < 10:
        return 3
    return 4

print(quarter_of(5), '\n')

def quarter_of2(month):
    return (month + 2) // 3

print(quarter_of2(5), '\n')

def quarter_of3(month):
    year ={1: [1, 2, 3], 2: [4, 5, 6], 3: [7, 8, 9], 4: [10, 11, 12]}
    for k, v in year.items():
        if month in v:
            return k

print(quarter_of3(5), '\n')


# Convert number to reversed array of digits
# Given a random non-negative number, you have to return the digits of this number within an array in reverse order.
#
# Example(Input => Output):
# 35231 => [1,3,2,5,3]
# 0 => [0]

def digitize(n):
    l = []
    for m in str(n):
        l.append(int(m))
    l.reverse()     # metoda [].reverse este pentru liste, iar functia reversed('text') este pentru stringuri
    return l

print(digitize(35231), '\n')

lista1 = [1, 2, 5, 8]
lista1.reverse()
print(lista1)
print([1, 2, 4, 7, 5].pop())

# Presupunem ca nu exista functia reverse()

def digitize2(n):
    l = []
    inx = len(str(n))
    while inx > 0:
        inx -= 1
        l.append(int(str(n)[inx]))

    return l

print(digitize2(35231))

print('textdirect', list(reversed('textdirect')), '\n')

def digitize3(n):
    return [int(m) for m in list(reversed(str(n)))]

print(digitize3(35231))

def digitize4(n):
    l = list(reversed(str(n)))
    l2 = []
    for m in l:
        l2.append(int(m))
    return l2

print(digitize4(35231))

lista2 = [2, 3, 4, 7, 9]

print([n ** 2 for n in lista2])
print(list(map(str, lista2)))  # functia map are doi parametri map(x, y) unde x e o functie, iar y e un iterabil (lista sau string)

import random as rd
import numpy as np
import math as mt
import matplotlib.pyplot as plt
import pandas as pd

#pentru a citi mai multe coloane 
desired_width = 320

pd.set_option('display.width', desired_width)

np.set_printoptions(linewidth = desired_width)

pd.set_option('display.max_columns',10)

# Reguli  de joc Black Jack!

# 1. Scopul este ca fiecare jucător să aibă o mână cu o valoare totală de 21 sau mai mare decat a
# adversarului / adversarilor, fără a depăși valoarea de 21
# 2. Valoarea fiecare cărți este, de fapt, cea trecută pe cartea de joc,
# excepție făcând următoarele cărți: valeții (J), damele (Q), popii (K). Aceste cărți au valoarea 10.
# În cazul așilor (A), aceste cărți au fie valoarea 1, fie valoarea 11.

# În cazul în care mâna ta este mai mare decât valoarea de 21, atunci vei pierde mâna respectivă – se spune că
# ești “BUST”. În cazul în care ai valoarea mai mică decât cea a dealerului, însă mâna acestuia depășește valoarea
# de 21, ai câștigat mâna respectivă.

# cele mai des utilizate opțiuni în jocul de Blackjack sunt HIT și STAND.
    #În toate situațiile în care ai un total mai mic de 11, vei cere încă o carte – HIT, pentru că este imposibil să
    # depășești 21, chiar și cu cea mai mare valoare venită la a treia carte: J, Q, K.
    # Stand este cand nu mai vrei carti si suma din mana ta este mai mare decat 15


dama = 10
popa = 10
valeti = 10
ass = 1 or 11
carti_de_joc = [2, 2, 2, 2, 3, 3, 3, 3, 4, 4, 4, 4, 5, 5, 5, 5, 6, 6, 6, 6, 7, 7, 7, 7, 8, 8, 8, 8, 9, 9, 9, 9, 10,
                10, 10, 10, ass, ass, ass, ass, valeti, valeti, valeti, valeti, dama, dama, dama, dama, popa, popa, popa,
                popa]

verdict = ['Stand', 'Bust', 'BlackJack']


print(len(carti_de_joc))

def rezultat():
    '''
    Am definit conditiile jocului
    '''

    scor = []

    while sum(scor) < 22:
        hit = rd.choice(carti_de_joc)  # functia random.choice() iti ia un element din un array
        print(hit)
        scor.append(hit)
        if sum(scor) > 15 and sum(scor) < 22:
            break

    if sum(scor) == 21:
        return verdict[2]
    elif sum(scor) < 15 and sum(carti_de_joc) > 21:
        return verdict[0]
    elif sum(scor) > 21:
        return verdict[1]
    else:
        return 'Trage o carte'

print(rezultat())
print(np.array([1, 2, 3, 4, 5, 'A']))


maps_hunedoara_dict = {
    'ZONA A': {
        'Strada': {
            'Avram Iancu': {
                'nr': range(21),
                'bloc': [133, 135, 'H2 - H5', 'Y2-1', 'Y2-2', 'X2-1', 'X2-2', 'Z2-1', 'Z2-2'],
                'apartamente': range(20),
                'etaje': range(4),
                'apartamente pe etaj': 4
            }
        },
        'Bdul Corvin': {
            'nr': range(17),
            'bloc': ['G2', 'D2' , 'D1', 'A4-1' , 'A4-1'],
            'apartamente': range(20),
            'apartamente pe etaj': 4
        },
        'Bdul Dacia': {
            'nr': range(1-43),
            'bloc': [139, 140, 2, 'V', 'V1 - V4', 'G1' , 'G3' ,'Gradinita Piticot' , 'J1'] ,
            'apartamente': range(20) ,
            'apartamente pe etaj':4
        },
        '-Bdul Traian':{
            'nr': range(47),
            'bloc':['T1 - T4' , 'Magazin Lidl', 'Scoala gimnaziala numarul 7' , 'C3' ,
                    'C4', 'bloc 1-5', 'I1' 'I2' , 'V1 - v6' 'I1' 'I2']
        },
        'str.M Viteazu':{
            'nr': range(46) ,
            'bloc': ['W' , 'U1 - U4', 'Piata Dunarea' , 'Y1- Y4', 'Gradinita Zori de zi' , 'X4 - X3'] ,
            'apartamente': range(12) , 'etaje': range(2), 'apartamente pe etaj':4
        }
    },
    'ZONA B':{
        'Strada':{
            'Aleea Mierlei':{
                'nr': range(11) ,
                'bloc': [ 'Catedrala Sfintii Imparati' ,'Primaria Municipiului Hunedoara' , 'Parcul Libertatii' ,
                          'Muzeul Comunismului']
            },
            'str.Al.Vlahuta':{
                'nr':range(17) ,
                'bloc': [range(15) , 'Piata eliberarii'] ,
                'ap' : range(40),
                'apartemant pe etaj':4
            } ,
            'Piata Eliberarii':{
                'nr': range(35) ,
                'bloc': [range(22)] ,
                'apartamente': range(20) ,
                'etaje': range(4) ,
                'apartamente pe etaj':4
            } ,
            'Gheorghe Baritiu':{
                'nr': range(32) ,
                'blocuri': [range(23), '2A - 14A'],
                'apartamente': range(20),
                'etaje': range(4) ,
                'apartamente pe etaj':4
            } ,
            '.N.Balcescu': {
                'nr': range(2,60) ,
                'cladiri':['Spitalul Municipal "Doctor Alexandru Simionescu"', 'Piata Florilor', 'Colegiul Tehnic M.C',
                        'Scoala Post Liceala Sanitara' , 'Stadionul Constructorul'],
                'parcuri': ['Parcul Corvin','Parcul Central']
            }
        }
    },
    'ZONA C':{
        'Strada':{
            'Aleea Chizid' :{
                'nr':range(22),
                'locuinte': 'case'} ,
            'Aleea Viitorului':{
                'nr': range(20) ,
                'bloc': ['F1 - F5','E1A - E11' , 'A1 - A1' , 'O1', 2 , 8 , 12 , 'D1', 'D2'],
                'apartamente': range(20) ,
                'etaje': range(4) ,
                'apartamente pe etaj':4
            },
                'Eliberarii': {
                'nr': range(31) ,
                'bloc': [range(1, 10), '1 - 10 BIS', 'U2' 'K1 - K5'] ,
                'etaje': range(10),
                'apartamente pe etaj':6 ,
                'apartamente': range(60)
                },
                'Elisabeta Margineanu':{ 'nr': range(2,30),
                }
        }
    }
}



dict_Hunedoara = {
    'Suprafata': 7.063,
    'Locuitori': 361657,
    'Densitate': 51.2,
    'Municipii': ['Brad', 'Deva', 'Hunedoara', 'Lupeni', 'Orastie', 'Petrosani', 'Aninoasa', 'Calan', 'Geoagiu',
                  'Petrila', 'Simeria', 'Uricani'],
    'Zona Muntoasa': True,
    'Orase': {}
}


dict_Hunedoara['Orase']['Hunedoara'] = {
    'Atractii turistice': 'Castelul Hunizilor',
    'Relief': 'deluros-muntos',
    'Resursele naturale': ['zăcăminte de piatră', 'minereuri feroase', 'lemn', 'talc'],
    'Relief antropic': ['Halda de zgura', 'cariera de piatra'],
    'Altitudine': 278,
    'primar PSD': True,
    'Fractionat': 'Cartiere'
}


dict_Hunedoara['Orase']['Hunedoara']['Cartiere'] = {
    'zone verzi': True,
    'parcuri' : True,
    'Nume Cartiere' : ['Micro 1', 'Micro 2', 'Micro 3', 'Micro 4', 'Micro 5', 'Micro 6', 'Micro 7'],
    'Comunitati rome' : True,
    'Gradinite': 20
}


dict_Hunedoara['Orase']['Hunedoara']['Cartiere']['Micro 2'] = {
    'Gradinite': 4,
    'Piata': True,
    'Restaurant': True,
    'Scoli': 2,
    'Licee': False,
    'Parcuri': True,
    'Comunitati Rome': False,
    'Nume strazi': ['Strada Munteniei', 'Strada Mihai Viteazu', 'Strada Transilvaniei', 'Strada Cerbului',
                    'Strada Moldova', 'Strada Caprioarei', 'Strada Avram Iancu'],
}


dict_Hunedoara['Orase']['Hunedoara']['Cartiere']['Micro 2']['Strada Transilvaniei'] = {
    'Numar Parcari': 5,
    'Scoala': True,
    'Parc': True,
    'Mgazine': True,
    'Zona Neasfaltata': False,
    'Numare': [1, 2, 3, 4, 5, 6 ,7 ,8, 9, 10, 12, 16, 19, 21, 23, 25, 29],
    'Nume Blocuri': ['C1', 'C2', 'C3', 'C4', 'V1', 'V2', 'V3', 'V4', 'V5', 'V6', 'V7'],
}


dict_Hunedoara['Orase']['Hunedoara']['Cartiere']['Micro 2']['Strada Transilvaniei'][6] = {
    'Numar Blocuri':  ['C1', 'C2', 'C3', 'C4'],
    'Zona Verde': True,
    'Parcare': 6,
    'Tomberoane': True,
    'Gropi in asfalt': False,
}


dict_Hunedoara['Orase']['Hunedoara']['Cartiere']['Micro 2']['Strada Transilvaniei'][6]['C3'] = {
    'Numar Scari': 3,
    'Nume Scari': ['A', 'B', 'C'],
    'Gard Viu': True,
    'Sarme pt rufe': True,
    'Restaurant': False,
    'Animale maidaneze': True,
}


dict_Hunedoara['Orase']['Hunedoara']['Cartiere']['Micro 2']['Strada Transilvaniei'][6]['C3']['B'] = {
    'Banca la scara': True,
    'Pomi fructiferi': ['Meri', 'Ciresi'],
    'Vita de vie': True,
    'Interfon': True,
    'Balustrada': True,
    'Pres la scara': True,
    'Tip bloc': 'bloc 4 etaje'
}


dict_Hunedoara['Orase']['Hunedoara']['Cartiere']['Micro 2']['Strada Transilvaniei'][6]['C3']['B']['bloc 4 etaje'] = {
    'Tip locuinte': 'Apartamente',
    'Numar scari interioare': 140,
    'Culoare pereti': 'Albi',
    'Culoare balustrada': 'Neagra',
    'Tablouri': True,
    'Cutii postale': True
}


dict_Hunedoara['Orase']['Hunedoara']['Cartiere']['Micro 2']['Strada Transilvaniei'][6]['C3']['B']['bloc 4 etaje']['Apartamente'] = {
    'Denumire etaje': ['Partier', 'Etaj 1', 'Etaj 2', 'Etaj 3', 'Etaj 4'],
    'Numar apartemente per etaj':4,
    'Animale de companie': True
}


dict_Hunedoara['Orase']['Hunedoara']['Cartiere']['Micro 2']['Strada Transilvaniei'][6]['C3']['B']['bloc 4 etaje']['Apartamente']['Partier'] = {
    'Apartamente': [21, 22, 23, 24],
    'Tablouri curent': True,
    'Animale de companie': True,
    'Camera de luat vederi': False
}


dict_Hunedoara['Orase']['Hunedoara']['Cartiere']['Micro 2']['Strada Transilvaniei'][6]['C3']['B']['bloc 4 etaje']['Apartamente']['Partier'][23] = {
    'compartimentare': 'Camere',
    'Usa la intrare': 'Metalica',
    'Suprafata': '120 mp2',
    'Geamuri': True,
    'Hol': True,
}


dict_Hunedoara['Orase']['Hunedoara']['Cartiere']['Micro 2']['Strada Transilvaniei'][6]['C3']['B']['bloc 4 etaje']['Apartamente']['Partier'][23]['Camere'] = {
    'Balcon': False,
    'Living': True,
    'Bucatarie': True,
    'Baie': 1,
    'Dormitoare': ['dormitor copil', 'dormitor principal'],
    'Culoare pereti': 'alb',

}


dict_Hunedoara['Orase']['Hunedoara']['Cartiere']['Micro 2']['Strada Transilvaniei'][6]['C3']['B']['bloc 4 etaje']['Apartamente']['Partier'][23]['Camere']['dormitor copil'] = {
    'pat': True,
    'Dulap': ['Dulap jucarii', 'Dulap Haine'],
    'Covor': 2,
    'Birou': True,
    'Perdele': True,
    'Canapea': False,
    'Televizor': False
}


dict_Hunedoara['Orase']['Hunedoara']['Cartiere']['Micro 2']['Strada Transilvaniei'][6]['C3']['B']['bloc 4 etaje']['Apartamente']['Partier'][23]['Camere']['dormitor copil']['Dulap jucarii'] = {
    'Papusi': 40,
    'Carti de colorat': True,
    'Acuarele': True,
    'Creioane colorate': True,
    'Slime': 8,
    'Haine papusi': True,
    'Masinute': False,
    'Cuburi Rubick': 6

}


print(dict_Hunedoara)

#programe_de_finantare = pd.read_csv('finantari.csv')
#print(programe_de_finantare)


finantari_neramburasabile = {
    'Nume program': ['PNRR', 'ADR', 'AFIR', 'POCU', 'Fonduri Elvetiene', 'GAL Hunedoara', 'AFM', 'POTJ'],
    'Sume_totale_alocate_mldE': [672.5, 600, 590, 490, 20, 5, 142, 843],
    'Buget_cheltuit': [222.45, 300.68, 100.20, 145.2, 5, 1, 60.89, 168.5],
    'Buget_ramas': [450.05, 299.32, 489.80, 344.80, 15, 4, 81.11, 674.50],
    'Beneficiari': ['UAT', 'UAT', 'UAT/ pers Juridice', 'ONG', 'UAT/ONG,Pers Juridice', 'UAT/ONG/Pers', 'Juridice/Pers.fizice',
                    'UAT/ONG/Pers Juridice'],
    'Exercitiu financiar': ['2021-2027', '2021-2027', '2021-2027', '2021-2027', '2021-2027', '2021-2027', '2021-2027',
                            '2021-2027'],
    'Cofinantare': [True, True, True, False, False, False, True, True,],
    'Perioada implementare maxima in ani': ['5 ani', '5 ani', '2 ani', '5 ani', '1 an', '3 ani', '4 ani', '5 ani'],
    'Perioada supraveghere': [True, True, True, True, False, True, True,True],
    'Rapoartare trimestriala' : [True, True, False, True, False, False, True, True],

}

print(finantari_neramburasabile, '\n')



finantare = pd.DataFrame(finantari_neramburasabile)

print(finantare, '\n')



finantare.index = ['LF1', 'LF2', 'LF3', 'LF4', 'LF5', 'LF6', 'LF7', 'LF8',]

print(finantare, '\n')



finatare_ext= pd.read_csv('finantare_TabMic.csv', index_col=0)

print(finatare_ext, '\n')


print(finatare_ext['Buget_ramas'], 'Bugetul ramas este: \n')


print(finatare_ext['Nume_program'], 'Program de finantare: \n')


print(finatare_ext.loc[['LF1', 'LF4']], 'finantari : \n')


print(finatare_ext.iloc[[1, 4, 8, 5]], '\n')

finantari = pd.read_csv('finantari.csv', encoding='ISO-8859-1') # encoding citeste diacritice

print(finantari)

print(finantari.iloc[[45]])

import random as rd
import numpy as np
import math as mt
import matplotlib.pyplot as plt
import pandas as pd

#pentru a citi mai multe coloane
desired_width = 320

pd.set_option('display.width', desired_width)

np.set_printoptions(linewidth = desired_width)

pd.set_option('display.max_columns',17)


situatie_proiecte = pd.read_csv('finantari.csv', encoding='ISO-8859-1')
print(situatie_proiecte, 'tabelul csv cu situatia pe tara accesare proiecte \n')


print(situatie_proiecte.head(16) , 'primele 1 pozitii din baza de date\n')  #nu include ultimul element deci e n+1


print(situatie_proiecte.tail(11) , 'ultimele 10 pozitii din baza de date \n')


print(situatie_proiecte.sample(5), '5 pozitii random (aleatorii) din baza de date \n')
# count = coloanele cu valori (cele ce nu sunt goale)
# mean = media proiectelor pe tara
# std = deviatia standard
# min = valoarea minima a unui proiect
# 25% = 25% din valoarea totala a proictelor
# 50% = 50% din valoarea totala a proiectelor
# 75 = 70 %din valoarea totala a proiectelor
# max = valoarea maxima a unui proiect

beneficiari = situatie_proiecte['Beneficiar']
print(beneficiari)
print(situatie_proiecte.iloc[20:150, [2, 9]] , 'pozitiile de la 20 la 50 , coloana bug total si Proj End date'),

#print(situatie_proiecte.describe('Bug elig benef'), ' \n')
print(situatie_proiecte.describe(), 'nu reusec sa iau decat coloana[0] \n')

print(situatie_proiecte.isnull())  #am verificat daca toate liniile sunt cu continut

#print(situatie_proiecte.sort_values(by = 'Bug total' , axis = 0, ascending = True, ignore_index = True),  'Aranjare in ordine rescatoare a coloanei Bug total \n')

print(situatie_proiecte.nlargest(5, "Cod SMIS"), 'Cel mai mare numar de pe coloana Cod SMIS \n \n \n')


print(situatie_proiecte.nsmallest(5,"Cod SMIS"), 'Cel mai mic numar de pe coloana Cod SMIS \n \n \n')


'''

Situatie proiecte Hunedora

'''



# Am cautat Hunedoara in baza de date si am listat pozitiile unde apare Hunedoara

print(situatie_proiecte[4:6],  'Situatia proiectelor in Hunedoara, poz 4 si 5 din baza de date \n')
print(situatie_proiecte[389:390], 'Situatia proiectelor in Hunedoara, poz 389 din baza de date \n')
print(situatie_proiecte[753:754] , 'Situatia proiectelor in Hunedoara, poz 753 din baza de date \n')
print(situatie_proiecte[903:904] , 'Situatia proiectelor in Hunedoara,poz 903 din baza de date \n')


#extragere de date cu metoda iloc[] pentru a vedea toate detaliile
print(situatie_proiecte.iloc[4])
print(situatie_proiecte.iloc[5])
print(situatie_proiecte.iloc[389])
print(situatie_proiecte.iloc[753])
print(situatie_proiecte.iloc[903])





# Am verificat de cate ori apare Hunedoara in beneficiari pentru a vedea daca am cautat bine
# Si am scos Hunedoara din lista de beneficiari

lista_beneficiari = list(beneficiari)
lista_beneficiari.count('Primaria Municipiului Hunedoara')
print(lista_beneficiari)
numar_proiecte = lista_beneficiari.count('Primaria Municipiului Hunedoara')
print('Municipiul Hunedoara in anul 2016 a accesat', {numar_proiecte}, 'proiecte \n')


sitProiecte_Hd = []
for orase in lista_beneficiari:
    if orase == 'Primaria Municipiului Hunedoara':
        sitProiecte_Hd.append(orase)
        print(sitProiecte_Hd , 'Am extras Hunedoara din csv coloana "Beneficiari"\n')


# cautam in coloana 'Bug elig benef' cheluielile eligibile aferente proiectelor din Mun Hunedoara

cheltuieli_eligibile = situatie_proiecte['Bug elig benef']
list_cheltuieli_eligibile = list(cheltuieli_eligibile)

print(list_cheltuieli_eligibile, 'lista ch eligibile \n')


list_cheltuieli_eligibile_HD = []
for suma in list_cheltuieli_eligibile:
    if suma == '668,575.67':
        list_cheltuieli_eligibile_HD.append(suma)
    elif suma == '31,097.94':
        list_cheltuieli_eligibile_HD.append(suma)
    elif suma == '195,012.65':
        list_cheltuieli_eligibile_HD.append(suma)
    elif suma == '170,864.62':
        list_cheltuieli_eligibile_HD.append(suma)
    elif suma == '87,795.29':
        list_cheltuieli_eligibile_HD.append(suma)

print(list_cheltuieli_eligibile_HD,'lista cheltuielilor eligibile aferente proiectului  Hd \n')


# am transformat din lista string in lista float cheltuielile eligibile

list_cheltuieli_eligibile_HD_float = []
for numar in list_cheltuieli_eligibile_HD:
    numarFloat = float(numar.replace(",", ""))
    list_cheltuieli_eligibile_HD_float.append(numarFloat)
print(list_cheltuieli_eligibile_HD_float)


# Calculam bugetul eligibil

total_eligibil = sum(list_cheltuieli_eligibile_HD_float)
print(total_eligibil, 'Suma totala eligibila a proiectelor\n')


# cautam in coloana 'Bug chelt neelig' cheluielile neeligibile aferente proiectelor din Mun Hunedoara

cheltuieli_neeligibile = list(situatie_proiecte['Bug chelt neelig'])
print(cheltuieli_neeligibile, 'Cheltuieli neeligibile aferente proiectelor Hd \n')


cheltuieli_neeligibile_hunedoara = []
for cn in cheltuieli_neeligibile:
    if cn == '8,102,374.15':
        cheltuieli_neeligibile_hunedoara.append(cn)
    elif cn == '570,216.68':
        cheltuieli_neeligibile_hunedoara.append(cn)
    elif cn == '699,463.50':
        cheltuieli_neeligibile_hunedoara.append(cn)
    elif cn == '2,096,362.57':
        cheltuieli_neeligibile_hunedoara.append(cn)
    elif cn == '1,016,329.75':
        cheltuieli_neeligibile_hunedoara.append(cn)


print(cheltuieli_neeligibile_hunedoara, 'Lista cheltuielilor neeligibile aferente proiectului  Hd \n')


# am transformat din lista string in lista float cheltuielile neeligibile

cheltuieli_neeligibile_hunedoara_float = []

for numarN in cheltuieli_neeligibile_hunedoara:
    numarFloatN = float(numarN.replace(',', ""))
    cheltuieli_neeligibile_hunedoara_float.append(numarFloatN)
print(cheltuieli_neeligibile_hunedoara_float)


# calculam totalul  neeligibil

total_neeligibil = sum(cheltuieli_neeligibile_hunedoara_float)
print(total_neeligibil,'Suma totala neeligibila a proiectelor\n' )


#calculam bugetul total

buget_total = total_eligibil + total_neeligibil
print(buget_total, 'Valoarea totala a proiectelor \n')


'''
Facem si pentru Deva ca sa putem compara

'''

alte_municipii = lista_beneficiari.count('Judetul Iasi')
print(alte_municipii)


#modificare csv colanele de buget din str in int

situatie_proiecte['Bug total'] = situatie_proiecte['Bug total' ].str.replace(',', "").astype(float)
print(situatie_proiecte['Bug total'], ' coloana Bug total nr float \n\n')


situatie_proiecte['Bug chelt neelig'] = situatie_proiecte['Bug chelt neelig'].str.replace(',', "").astype(float)
print(situatie_proiecte['Bug chelt neelig'], ' Coloana cheltuieli neeligibile nr floar\n\n')


situatie_proiecte['Bug elig benef'] = situatie_proiecte['Bug elig benef'].str.replace(',', "").astype(float)
print(situatie_proiecte['Bug elig benef'], ' Coloana cheltuieli eligibile nr floar\n\n')


print(situatie_proiecte, 'Situatie proiecte cu numere float \n')

# aflam cine are cea mai mare suma totala a proiectelor

cea_mai_mare_suma = situatie_proiecte['Bug total'].max()
print(cea_mai_mare_suma, 'cea mai mare valoare\n')

#cea extragem judetul cu cea mai mare suma

top_proiect = situatie_proiecte[situatie_proiecte['Bug total'] == cea_mai_mare_suma]
print(top_proiect, ' municipiul cu cel mai mare buget total \n')

#extragem cea mai mica valoare

cea_mai_mica_suma = situatie_proiecte['Bug total']. min()
min_proiect = situatie_proiecte[situatie_proiecte['Bug total'] == cea_mai_mica_suma]
print(cea_mai_mica_suma, 'cea mai mica valoare \n')


#cea extragem judetul cu cea mai mica suma

min_proiect = situatie_proiecte[situatie_proiecte['Bug total'] == cea_mai_mica_suma]
print(min_proiect, ' municipiul cu cel mai mare buget total \n')


# aflam cine a terminat de implementat proiectul

proiecte_implementate = situatie_proiecte['Stare']
print(proiecte_implementate)

sit_proiecte_implementate = situatie_proiecte[situatie_proiecte['Stare'] == 'Completed']
print(sit_proiecte_implementate, 'Municipii/Judete care au terminat de implementat proiectele')


#Proiecte in curs de implementare

proiecte_in_curs = situatie_proiecte['Stare']
proiecte_in_curs_impl = situatie_proiecte[situatie_proiecte['Stare'] == 'Approved']
print(proiecte_in_curs_impl, 'Municipii/Judete care sunt in curs de implementare\n')


# Sume totale proicet  proiecte finalizare
#start = sit_proiecte_implementate
#coloane = 'Bug total'
#sume_totale_proiect_finalizat = start[coloane].sum()

sume_totale_proiect_finalizat = sit_proiecte_implementate['Bug total'].sum()
print(sume_totale_proiect_finalizat, 'Suma totala a proiectelor implementate \n')


# Sume totale proiecte in curs de implementare

#rand = proiecte_in_curs_impl
#sume_totale_proiecte_in_curs = rand[coloane].sum()
#print(sume_totale_proiecte_in_curs, 'suma toatala a proiectelor in curs de implementare\n')

sume_totale_proiecte_in_curs = proiecte_in_curs_impl['Bug total'].sum()
print(sume_totale_proiecte_in_curs, 'suma toatala a proiectelor in curs de implementare\n')


#aflam daca suma proiectelor implementate este mai mare ca si suma proiectelor in implementare

suma_mai_mare = sume_totale_proiecte_in_curs > sume_totale_proiect_finalizat
print(suma_mai_mare, ' sumele totale ale proiectelor in implementare nu este mai mare decat suma totala a proiectelor finalizate\n')

#creem csv pentru proiecte finalizate si pt proiecte in curs

sit_proiecte_implementate.to_csv('Proiecte finalizate.csv')
proiecte_completed = pd.read_csv('Proiecte finalizate.csv')

proiecte_in_curs.to_csv('Proiecte in curs de implementare.csv')
proiecte_aroved = pd.read_csv('Proiecte in curs de implementare.csv')


#calculam finantarea nerabusarbila la proiectele finalizate



#sortam sumele in cele 2 csv nou create

proiecte_completed_sort = proiecte_completed.sort_values(by = ['Bug total', 'Bug chelt neelig', 'Bug elig benef'], ascending = True)
print(proiecte_completed_sort, 'sume sortate la csv proiecte finalizate\n')


proiecte_aroved = proiecte_completed.sort_values(by = ['Bug total', 'Bug chelt neelig', 'Bug elig benef'], ascending = True)
print(proiecte_aroved, 'sume sortate la csv proiecte in curs de finalizare\n')


class Carte_de_vizita:
    def __init__(self, nume_init, prenume_init, email_init, meserie_init, program_init, telefon_init=12345, foto_init="poza.jpg"):
        self.nume = nume_init
        self.prenume = prenume_init
        self.telefon = telefon_init
        self.adresa_email = email_init
        self.meserie_actuala = meserie_init
        self.orar_functionare = program_init
        self.fotografie = foto_init

        print('Metoda constructor __init__ a fost apelata')

    def descriere(self):
        print(f'Pe cartea de vizita gasim elemenetele {self.nume} {self.prenume} {self.telefon}'
              f' {self.adresa_email}, {self.meserie_actuala}, {self.orar_functionare}, {self.fotografie}')

elemente_promovare = Carte_de_vizita('Ion', 'CIolacu', 'cio@m.com', 'Sofer', 'Luni - Joi')
elemente_promovare.descriere()


class Fisa_postului:
    def __int__(self, atributii_init, program_de_lucru_init, responsabilitati_init, ore_de_lucru_saptamanale_init,
                tinuta_init):
          self.atributii = atributii_init
          self.orar = program_de_lucru_init
          self.responsabilitati = responsabilitati_init
          self.ore_saptamanal = ore_de_lucru_saptamanale_init
          self.imbracaminte = tinuta_init


    def descriere(self):
       print(f'in fisa postului regasim urmatoarele elemente: {self.atributii} {self.orar}, {self.responsabilitati},'
             f'{self.ore_saptamanal} {self.imbracaminte}')


class CV:
    def __init__(self, numar_telefon_init, adresa_email_init, adresa_init, cod_postal_init, data_nastere_init,
                experinta_anteriora_init, loc_de_munca_actual_init, nivel_de_studii_init, limbi_straine_vorbite_init,
                pemis_De_conducere_init, alte_cursuri_init,competente_genonale_init, descriere_genonala_init):
        self.telefon = numar_telefon_init
        self.email = adresa_email_init
        self.adresa_domiciliu = adresa_init
        self.cod_postal_domiciliu = cod_postal_init
        self.zi_nastere = data_nastere_init
        self.experienta = experinta_anteriora_init
        self.job_actual = loc_de_munca_actual_init
        self.studii = nivel_de_studii_init
        self.limbi_vorbite = limbi_straine_vorbite_init
        self.permis = pemis_De_conducere_init
        self.cursuri = alte_cursuri_init
        self.competente = competente_genonale_init
        self.despre_tine = descriere_genonala_init

elemente_promovare3 = CV
print(elemente_promovare3)


class ManagementProiect:
    VALOARE_ELIGIBILA = 30000

    def __init__(self, date_identificare_init, autoritate_contractanta_init, achizitii_init, titlu_proiect_init,
                 valoare_totala_proiect_init, perioada_implementare_init ='2024-2025'):
        self.tilu_proiect = titlu_proiect_init
        titlu_proiect_init('Doatare')
        self.date_identificare = date_identificare_init
        self.autoritate_contractanta = autoritate_contractanta_init
        autoritate_contractanta_init('AFIR')
        self.perioada_implementare = perioada_implementare_init
        self.achizitii = achizitii_init
        achizitii_init = sum(self.bunuri_achizitionate(laptop=2 , imprimanta=3, all_in_one=2, mobilier=1000))
        self.valoare_proiect = valoare_totala_proiect_init
        valoare_totala_proiect_init(30000)
        if achizitii_init >= ManagementProiect.VALOARE_ELIGIBILA:
            print('Cheltuiala eligibila')
        else:
            'Cheltuieli neeligibile'
        print('Metoda constructor __init__ a fost apelata')


    def date_identificare(self, data, nr_contract, moneda):
        self.data = data
        data('04.03.2024')
        self.nr_contract = nr_contract
        nr_contract(1446)
        self.moneda = moneda
        moneda('Euro')


    def bunuri_achizitionate(self, laptop, imprimanta, all_in_one,mobilier):
        self.laptop = laptop
        self.laptop(500)
        self.imprimanta = imprimanta
        self.imprimanta(3000)
        self.all_in_one = all_in_one
        self.all_in_one(9000)
        self.mobilier = mobilier
        self.mobilier(20000)

management = ManagementProiect







