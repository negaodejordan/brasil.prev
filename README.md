#brasil.prev
#Banco_Imobiliário

import random

play1 = [ #IMPULSIVO
    300, #saldo
    [], #propridades conquistadas
    [0], #posicionamento no tabuleiro
]
play2 = [ #EXIGENTE
    300, #saldo
    [], #propridades conquistadas
    [0], #posicionamento no tabuleiro
]
play3 = [ #CAUTELOSO
    300, #saldo
    [], #propridades conquistadas
    [0], #posicionamento no tabuleiro
]
play4 = [ #ALEATORIO
    300, #saldo
    [], #propridades conquistadas
    [0], #posicionamento no tabuleiro
]

lista_propriedades = [
#   ('nome da rua', preço da rua, aluguel)
    ('Inicio'),
    ('01 Av. Paulista', 236, 315),
    ('02 Av. Engenheiro Luís Carlos Berrini', 200, 10),
    ('03 Av. Presidente Juscelino Kubitschek', 516, 70),
    ('04 Av. Indianópolis', 713, 439),
    ('05 Rua Tijuco Preto', 800, 60),
    ('06 Rua Tuiuti', 610, 795),
    ('07 Av. Paes de Barro', 367, 746),
    ('08 Rua do Oratório', 794, 102),
    ('09 Av. Aricanduva', 460, 399),
    ('10 Av. Luiz Americano', 529, 460),
    ('11 Av. Washington Luís', 427, 30),
    ('12 Av. Interlagos', 496, 567),
    ('13Av. Yervant Kissajikian', 867, 889),
    ('14 Av. Lins de Vasconcelos', 110, 98),
    ('15 Av. Jabaquara', 703, 676),
    ('16 Av. Domingos de Moraes', 572, 50),
    ('17 Av. Iguatemi', 216, 418),
    ('18 Rua Luís Dr.Alves', 819, 309),
    ('19 Av. Afonso de Sampaio e Sousa', 800, 400),
    ('20 Rua Inacio Monteiro', 1000, 500),
]

contador_rounds = 1
print('-= Rodada {} =-\n'.format(contador_rounds))

dadosP1 = random.randint(1,6)
DadosP1 = random.randint(1,6) #dado para somaçao no final
play1[2] = dadosP1 #player andou
print('O player 1 está na casa:',play1[2])
print('Saldo:',play1[0])
print('O jogador 1 está em',lista_propriedades[play1[2]][0]) #vai falar onde o player está

if lista_propriedades[play1[2]] in lista_propriedades: #VERIFICAÇÃO DE RUA
    print('A avenida está livre para compra')
    print('Avenida está alugada, pagar aluguel')
else:
    aluguelP1 = lista_propriedades[play1[2]][2]
    play1[0] = play1[0] - aluguelP1  #PAGAMENTO DE ALUGUEL

    if play1[0] <= 0: #VERIFICACAO DE PERDA DO JOGO
        print('O jogador 1 foi listado no SERASA, ELIMINADO')


print('-'*30)

dadosP2 = random.randint(1,6)
DadosP2 = random.randint(1,6) #dado para somaçao no final
play2[2] = dadosP2 #player andou
print('O player 2 está na casa:',play2[2])
print('Saldo:',play2[0])
print('O jogador 2 está em',lista_propriedades[play2[2]][0]) #vai falar onde o player está
if lista_propriedades[play1[2]] in lista_propriedades:
    print('A avenida está livre para compra')
    print('Avenida está alugada, pagar aluguel')
else:
    aluguelP2 = lista_propriedades[play2[2]][2]
    play2[0] = play2[0] - aluguelP2  # PAGAMENTO DE ALUGUEL

    if play2[0] <= 0:  # VERIFICACAO DE PERDA DO JOGO
        print('O jogador 2 foi listado no SERASA, ELIMINADO')

print('-'*30)

dadosP3 = random.randint(1,6)
DadosP3 = random.randint(1,6) #dado para somaçao no final
play3[2] = dadosP3 #player andou
print('O player 3 está na casa:',play3[2])
print('Saldo:',play3[0])
print('O jogador 3 está em',lista_propriedades[play3[2]][0]) #vai falar onde o player está
if lista_propriedades[play3[2]] in lista_propriedades:
    print('A avenida está livre para compra')
    print('Avenida está alugada, pagar aluguel')
else:
    aluguelP3 = lista_propriedades[play3[2]][2]
    play3[0] = play3[0] - aluguelP3  # PAGAMENTO DE ALUGUEL

    if play3[0] <= 0:  # VERIFICACAO DE PERDA DO JOGO
        print('O jogador 3 foi listado no SERASA, ELIMINADO')

print('-'*30)

dadosP4 = random.randint(1,6)
DadosP4 = random.randint(1,6) #dado para somaçao no final
play4[2] = dadosP4 #player andou
print('O player 4 está na casa:',play4[2])
print('Saldo:',play4[0])
print('O jogador 4 está em',lista_propriedades[play4[2]][0]) #vai falar onde o player está

if lista_propriedades[play4[2]] in lista_propriedades: #VERIFICAÇAO DE RUA
    print('A avenida está livre para compra')
    print('Avenida está alugada, pagar aluguel')
else:
    aluguelP4 = lista_propriedades[play4[2]][2]
    play4[0] = play4[0] - aluguelP4  # PAGAMENTO DE ALUGUEL

    if play4[0] <= 0:  # VERIFICACAO DE PERDA DO JOGO
        print('O jogador 4 foi listado no SERASA, ELIMINADO')


while True:
    #===============================================================================================#
    contador_rounds += 1
    print('\n','='*30,'\n','\n-= Rodada {} =-'.format(contador_rounds))

    DADOSP1 = random.randint(1, 6)
    if play1[0] <= 0:
        print('O jogador 1 foi listado no SERASA, ELIMINADO')
    else:
        if play1[2] >= 21:
            play1[2] = play1[2] - 20
        play1[2] += DADOSP1
        if play1[2] >= 21:
            play1[2] = play1[2] - 20
        print('O player 1 está na casa:',play1[2])
        print('Saldo:',play1[0])
        print('O jogador está em',lista_propriedades[play1[2]][0]) #vai falar onde o player está

        if lista_propriedades[play1[2]] in lista_propriedades: #VERIFICAÇAO DE RUA
            print('A avenida está livre para compra')
            print('Avenida está alugada, pagar aluguel')
        else:
            aluguelP1 = lista_propriedades[play1[2]][2]
            play1[0] = play1[0] - aluguelP1  # PAGAMENTO DE ALUGUEL
            if play1[0] <= 0:  # VERIFICACAO DE PERDA DO JOGO
                print('O jogador 1 foi listado no SERASA, ELIMINADO')

    print('-'*30)

    DADOSP2 = random.randint(1, 6)
    if play2[0] <= 0:
        print('O jogador 2 foi listado no SERASA, ELIMINADO')
    else:
        if play2[2] >= 21:
            play2[2] = play2[2] - 20
        play2[2] += DADOSP2
        if play2[2] >= 21:
            play2[2] = play2[2] - 20
        print('O player 2 está na casa:',play2[2])
        print('Saldo:',play2[0])
        print('O jogador está em',lista_propriedades[play2[2]][0])  # vai falar onde o player está

        if lista_propriedades[play2[2]] in lista_propriedades: #VERIFICAÇAO DE RUA
            print('A avenida está livre para compra')
            print('Avenida está alugada, pagar aluguel')
        else:
            aluguelP2 = lista_propriedades[play1[2]][2]
            play2[0] = play2[0] - aluguelP2 # PAGAMENTO DE ALUGUEL
            if play2[0] <= 0:  # VERIFICACAO DE PERDA DO JOGO
                print('O jogador 2 foi listado no SERASA, ELIMINADO')

    print('-'*30)

    DADOSP3 = random.randint(1, 6)
    if play3[0] <= 0:
        print('O jogador 3 foi listado no SERASA, ELIMINADO')
    else:
        if play3[2] >= 21:
            play3[2] = play3[2] - 20
        play3[2] += DADOSP3
        if play3[2] >= 21:
            play3[2] = play3[2] - 20
        print('O player 3 está na casa:',play3[2])
        print('Saldo:',play3[0])
        print('O jogador está em',lista_propriedades[play3[2]][0])  # vai falar onde o player está

        if lista_propriedades[play1[2]] in lista_propriedades: #VERIFICAÇAO DE RUA
            print('A avenida está livre para compra')
            print('Avenida está alugada, pagar aluguel')
        else:
            aluguelP3 = lista_propriedades[play3[2]][2]
            play3[0] = play3[0] - aluguelP3  # PAGAMENTO DE ALUGUEL
            if play3[0] <= 0:  # VERIFICACAO DE PERDA DO JOGO
                print('O jogador 3 foi listado no SERASA, ELIMINADO')

    print('-'*30)

    DADOSP4 = random.randint(1,6)
    if play4[0] <= 0:
        print('O jogador 4 foi listado no SERASA, ELIMINADO')
    else:
        if play4[2] >= 21:
            play4[2] = play4[2] - 20
        play4[2] += DADOSP4
        if play4[2] >= 21:
            play4[2] = play4[2] - 20
        print('O player 4 está na casa:',play4[2])
        print('Saldo:',play4[0])
        print('O jogador está em',lista_propriedades[play4[2]][0])  # vai falar onde o player está

        if lista_propriedades[play1[2]] in lista_propriedades: #VERIFICAÇAO DE RUA
            print('A avenida está livre para compra')
            print('Avenida está alugada, pagar aluguel')
        else:
            aluguelP4 = lista_propriedades[play4[2]][2]
            play4[0] = play4[0] - aluguelP4  # PAGAMENTO DE ALUGUEL
            if play4[0] <= 0:  # VERIFICACAO DE PERDA DO JOGO
                print('O jogador 4 foi listado no SERASA, ELIMINADO')

    if contador_rounds == 1000:
        break
    else:
        pass
