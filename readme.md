*CRIAÇÃO DO AMBIENTE*
Primeiro, é necessário importar o pygame no repositório com:
import pygame
from pygame.locals import *
from sys import exit (Essa função diz que a janela é fechada ao clicar em 'exit')

Com 'pygame.init', o jogo é basicamente 'iniciado'.

Na variável tela, é possível adicionar as dimensões da janela do jogo diretamente ou através de variáveis.
Para o jogo não travar, é necessário ter um loop principal. O código abaixo é o PADRÃO para o loop principal:
'''''''''''''''while True:
               for event in pygame.event.get():
                 if event.type == pygame.QUIT:
                 pygame.quit()
                 quit()
               pygame.display.update()''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

É DENTRO DO '''FOR''' QUE SE COLOCA OS EVENTOS QUE ACONTECEM DURANTE O JOGO!!!

*CRIAÇÃO DE OBJETOS*
Para a criação de objetos, deve-se utilizar a lógica do PLANO CARTESIANO. 
X = EIXO HORIZONTAL; Y = EIXO VERTICAL (PARA BAIXO).
Também é possível inserir cor no objeto, isso é feito com a sigla RGB(Red,Green,Blue), que varia de 0 a 255.
''''''''''''''' pygame.draw.rect(tela, (255,0,0), (200,300,40,30))''''''''''''''''''''''''''''''''''''''''''
Usa-se 'rect' para RETÂNGULO, 'circle' para CÍRCULO, line para LINHA.
'''''''''''''''''''''''''pygame.draw.rect(tela,(255,0,0),(0,300,40,30))
                         pygame.draw.circle(tela, (0,255,0), (300,300), 40)
                         pygame.draw.line(tela, (255,255,40), (400, 300), (500, 300), (10))'''''''''''''''''
primeiro parâmetro = local
segundo parâmetro = cor
terceiro parâmetro = dois números para POSIÇÃO no local, e os últimos dois para o TAMANHO do objeto.

''''''''''''tela.fill((0,0,0))''''''''''' Para 'limpar' a tela quando o objeto anda.

*OBJETO SE MOVE SOZINHO*
if y>= altura:
    y = 0
y = y + 1

*OBJETO SENDO CONTROLADO, PORÉM SEM PRESSIONAR A TECLA*
if event.type == KEYDOWN:
    if event.key == K_a:
        x = x - 20
    if event.key == K_d:
        x = x + 20
    if event.key == K_w:
        y = y - 20
    if event.key == K_s:
        y = y + 20


*OBJETO SENDO CONTROLADO COM PRESSÃO NA TECLA*
    if pygame.key.get_pressed()[K_a]:
       x = x - 20
    if pygame.key.get_pressed()[K_d]:
       x = x + 20
    if pygame.key.get_pressed()[K_w]:
       y = y - 20
    if pygame.key.get_pressed()[K_s]:
       y = y + 20
Neste caso, o objeto sai da tela. Para isso não acontecer, usar o código:
    if pygame.key.get_pressed()[K_a]:
        if x > 0:
            x -= 20
    if pygame.key.get_pressed()[K_d]:
        if x < (largura - 40):
            x += 20
    if pygame.key.get_pressed()[K_w]:
        if y > 0:
            y -= 20
    if pygame.key.get_pressed()[K_s]:
        if y < (altura - 50):
            y += 20 


*COLISÕES*
if ret_vermelho.colliderect(ret_roxo):
        print('colisão')''''''''''''''
Código acima paa testar a colisão.

Raindint para escolha de pontos aleatórios no plano.
''''''pygame.font.get_fonts()''''''' PARA SABER AS FONTES DISPONÍVEIS (não funcionou)
