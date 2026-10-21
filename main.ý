
import tkinter as tk
import random
import math

LARGURA = 700
ALTURA = 600

janela = tk.Tk()
janela.title("carolina pantoja miranda💗")
janela.configure(bg="black")

tela = tk.Canvas(
    janela,
    width=LARGURA,
    height=ALTURA,
    bg="#03030a",
    highlightthickness=0
)
tela.pack()

# Criar estrelas
estrelas = [
    (
        random.randint(0, LARGURA),
        random.randint(0, ALTURA),
        random.choice([1, 1, 2])
    )
    for _ in range(100)
]

def desenhar():
    tela.delete("all")

    # Fundo estrelado
    for x, y, tamanho in estrelas:
        brilho = random.choice(["#ffffff", "#777799", "#333355"])
        tela.create_oval(
            x, y, x + tamanho, y + tamanho,
            fill=brilho, outline=""
        )

    # Formato matemático do coração
    escala = 14
    pontos = []

    for i in range(500):
        t = i * 2 * math.pi / 500

        x = 16 * math.sin(t) ** 3
        y = (
            13 * math.cos(t)
            - 5 * math.cos(2 * t)
            - 2 * math.cos(3 * t)
            - math.cos(4 * t)
        )

        pontos.append((
            LARGURA / 2 + x * escala,
            ALTURA / 2 - y * escala
        ))

    # Coração feito de pequenos caracteres
    caracteres = "@#%*+:. "
    for x, y in pontos[::3]:
        char = random.choice(caracteres[:6])
        cor = random.choice([
            "#ff4fa3", "#ff80bf", "#ffb6dc"
        ])
        tela.create_text(
            x, y,
            text=char,
            fill=cor,
            font=("Courier", 10, "bold")
        )

    # Mensagem central
    tela.create_text(
        LARGURA / 2, ALTURA - 65,
        text="Carolina Pantoja ♡",
        fill="#ff80bf",
        font=("Courier", 19, "bold")
    )

    janela.after(120, desenhar)

desenhar()
janela.mainloop()

