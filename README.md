# teoria-musical-para-Autista
# Notas-Musicas-com-identifica-o-para-Autistas

# Primeiro Eu importei as 2 blibliotecas abaixo

import tkinter as tk
import winsound  # Para reprodução de sons no Windows
# Importe outras bibliotecas necessárias para reprodução de som em outros sistemas operacionais

# Aqui está o Dicionário com as notas musicais e suas frequências em Hz
notas_musicais = {
    'C': 261.63, 'C#': 277.18, 'D': 293.66, 'D#': 311.13,
    'E': 329.63, 'F': 349.23, 'F#': 369.99, 'G': 392.00,
    'G#': 415.30, 'A': 440.00, 'A#': 466.16, 'B': 493.88
}

# Eu Utilizei a função winsound.Beep (para Windows) para reproduzir o som da nota musical.
def tocar_nota(nota):
    frequencia = notas_musicais.get(nota, 0)
    if frequencia > 0:
        winsound.Beep(int(frequencia), 300)  # Reproduz o som da nota por 300ms
    else:
        print(f"Nota {nota} não encontrada.")

# Criei uma janela principal (tk.Tk()), e define o título e criei botões para cada nota musical, usando cores diferentes (cores_notas).
root = tk.Tk()
root.title("Notas Musicais para Autistas")

# Aqui eu Defini as cores para as notas (exemplo: cores diferentes para cada nota)
cores_notas = {
    'C': 'red', 'C#': 'orange', 'D': 'yellow', 'D#': 'green',
    'E': 'cyan', 'F': 'blue', 'F#': 'purple', 'G': 'magenta',
    'G#': 'pink', 'A': 'brown', 'A#': 'gray', 'B': 'teal'
}

# Aqui Eu Criei botões para cada nota musical
for nota, cor in cores_notas.items():
    btn_nota = tk.Button(root, text=nota, bg=cor, padx=20, pady=10,
                         command=lambda n=nota: tocar_nota(n))
    btn_nota.pack(padx=10, pady=5)

# Inicia o loop principal da interface gráfica com root.mainloop().
root.mainloop()
