from random import randrange
def piskvorky1d (pole):
    while True:
        def tah_hrace(pozice, symbol):
                pole=pole[:pozice-1]+"x"+pole[pozice:]
                return pole
                if "x" or "o" in pole[pozice-1]:
                    return tah_hrace((int(input("Policka uz je obsazena, zkus znovy: "))), "x")
                elif pozice > 20 or pozice < 1:
                    return tah_hrace((int(input("Cislo je prilis velke, zkus znovu: "))), "x")
        print(tah_hrace(int(input('Zadej pozice: '))), "x")
        if 'xxx' in pole:
            print('x')
            break
        if 'ooo' in pole:
            print("o")
            break
        if '-' not in pole:
            print('!')
            break
        else:
            print ('-')
        def tah_pocitace(pozice, symbol):
            if "x" or "o" not in pole[pozice-1]:
                pole=pole[:pozice-1]+"o"+pole[pozice:]
                return pole
            else:
                return tah_pocitace
        print(tah_pocitace(randrange(0,20), "o"))
piskvorky1d("-"*20)
