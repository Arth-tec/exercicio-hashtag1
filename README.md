import pyautogui
import time
import pandas

# pyautogui.write -> escreve um texto
# pyautogui.click -> clicar com o mouse
# pyautogui.press -> apertar uma tecla
# pyautogui.hotkey -> apertar um atalho do teclado (ctrl, C)

pyautogui.PAUSE = 0.3

# entrar no navegador

pyautogui.press("win")
pyautogui.write("nome do navegador")
pyautogui.press("enter")

# entrar no site (site de teste)
link = "https://dlp.hashtagtreinamentos.com/python/intensivao/login"

pyautogui.write(link)
pyautogui.press("enter")

time.sleep(1)

# clicar na interface do site

#codigo para pegar as coordenadas do mouse

#import pyautogui
#import time

#time.sleep(2)
#print(pyautogui.position())

pyautogui.click(x=487, y=371)

# fazer loguin

pyautogui.write("e-mail.com123")
pyautogui.press("tab")
pyautogui.write("senha123")
pyautogui.press("tab")
pyautogui.press("enter")

lista = pandas.read_csv("produtos.csv")
print(lista)

linha = 0

for linha in lista.index:

    # clickar para cadastrar os produtos

     pyautogui.click(x=501, y=256)

    # digitar os produtos

     codigo = lista.loc[linha, "codigo"]

     pyautogui.write(str(codigo))
     pyautogui.press("tab")

     marca = lista.loc[linha, "marca"]

     pyautogui.write(str(marca))
     pyautogui.press("tab")

     tipo = lista.loc[linha, "tipo"]

     pyautogui.write(str(tipo))
     pyautogui.press("tab")

     categoria = lista.loc[linha, "categoria"]
     pyautogui.write(str(categoria))
     pyautogui.press("tab")

     preco = lista.loc[linha, "preco_unitario"]

     pyautogui.write(str(preco))
     pyautogui.press("tab")
    
     custo = lista.loc[linha, "custo"]

     pyautogui.write(str(custo))
     pyautogui.press("tab")

     obs = lista.loc[linha, "obs"]
     if not pandas.isna(obs):
        pyautogui.write(str(obs))
     pyautogui.press("tab")

     pyautogui.press("enter")
     pyautogui.scroll(5000)

