TEXTS = ['''Situated about 10 miles west of Kemmerer,
Fossil Butte is a ruggedly impressive
topographic feature that rises sharply
some 1000 feet above Twin Creek Valley
to an elevation of more than 7500 feet
above sea level. The butte is located just
north of US 30N and the Union Pacific Railroad,
which traverse the valley. ''',

'''At the base of Fossil Butte are the bright
red, purple, yellow and gray beds of the Wasatch
Formation. Eroded portions of these horizontal
beds slope gradually upward from the valley floor
and steepen abruptly. Overlying them and extending
to the top of the butte are the much steeper
buff-to-white beds of the Green River Formation,
which are about 300 feet thick.''',

'''The monument contains 8198 acres and protects
a portion of the largest deposit of freshwater fish
fossils in the world. The richest fossil fish deposits
are found in multiple limestone layers, which lie some
100 feet below the top of the butte. The fossils
represent several varieties of perch, as well as
other freshwater genera and herring similar to those
in modern oceans. Other fish such as paddlefish,
garpike and stingray are also present.''']




registrovani = {'bob': '123', 'ann': 'pass123', 'mike': 'password123', 'liz': 'pass123'}


print('=' * 30)
print('Vitejte v aplikaci,prosim prihlaste se:')



uzivatel = input('Uzivatel: ')
kod = input('Heslo: ')

if registrovani.get(uzivatel) != kod:
    print('Neexistujici uzivatel nebo kod')
    quit()





print('=' * 30)
print('.')
vyber = int(input('Vloz cisla 1,2 nebo 3: '))
print('-' * 40)
text = TEXTS[vyber -1]
neupraveny_text = text.split()

print (neupraveny_text)

words = []


while neupraveny_text:
    word = neupraveny_text.pop()

    word = word.strip('.,:/;')

    words.append(word)


print( str(len(words)) + ' slov je v textu.')

titlecase = 0
lowercase = 0
uppercase = 0
numeric   = 0
pocet    = {}
num_sum   = 0
i = 0
while i < len(words):
    if words[i].istitle():
        titlecase += 1
    elif words[i].isupper():
        uppercase += 1
    elif words[i].islower():
        lowercase += 1
    elif words[i].isnumeric():
        numeric += 1
        num_sum += float(words[i])

    p = len(words[i])
    pocet[p] = pocet.get(p, 0) + 1
    i +=1

print('There are ' + str(titlecase) + ' titlecase words')
print('There are ' + str(uppercase) + ' uppercase words')
print('There are ' + str(lowercase) + ' lowercase words')
print('There are ' + str(numeric) + ' numeric strings')
print('-' * 40)


delky = sorted(pocet)
i= 0
while i < len(delky):
    delka = delky[i]
    frequence = pocet[delka]
    if len(str(delka)) == 1:
        str_len = ' ' + str(delka)
    else:
        str_len = str(delka)
    print(str_len, '*' * frequence)
    i = i + 1

print('-' * 30)
print('Sectena cisla v textu: ' + str(num_sum))
print(':=]' * 30)