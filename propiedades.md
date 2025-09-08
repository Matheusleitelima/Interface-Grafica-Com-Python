# Principais Widgets do Tkinter

De acordo com **Meier (2015)**, os principais widgets da biblioteca **Tkinter** são:

---

## 📌 Lista de Widgets

### 🔘 Botão (Button)
Usado para exibir botões na aplicação.  
Exemplo: confirmar uma ação de salvar os dados.

### 🖼️ Telas (Canvas)
Usado para desenhar formas, como linhas, ovais, polígonos e retângulos.

### ☑️ Botão de verificação (Checkbutton)
Usado para exibir várias opções como caixas de seleção.  
O usuário pode selecionar várias opções ao mesmo tempo.

### ✍️ Entrada de texto (Entry)
Usado para exibir uma caixa de texto de linha única, onde o usuário pode digitar valores.

### 📦 Quadros (Frame)
Usado como um **widget de contêiner**, ou seja, outros componentes podem ser adicionados a ele para organizar a interface.

### 🏷️ Rótulo (Label)
Usado para fornecer uma legenda de linha única para outros widgets.  
Também pode conter imagens.

### 📋 Caixa de listagem (Listbox)
Usado para fornecer uma lista de opções para o usuário.

### 📂 Menubutton
Usado para exibir opções em um menu.

### 📑 Menu
Fornece várias possibilidades de comandos para o usuário, geralmente exibidos dentro de um **Menubutton**.

### 💬 Mensagem (Message)
Exibe uma mensagem de texto e pode ser acompanhado de um botão para o usuário confirmar uma ação.

### 🔘 Botão de rádio (Radiobutton)
Exibe várias opções como botões de rádio.  
O usuário pode selecionar apenas **uma opção** por vez.

### 🎚️ Escala (Scale)
Fornece um widget de controle deslizante.

### ↕️ Barra de rolagem (Scrollbar)
Adiciona capacidade de rolagem a vários widgets.

### 📝 Texto (Text)
Usado para exibir texto em **várias linhas**.

### 🪟 Toplevel
Fornece um contêiner de janela separado.

### 🔢 Spinbox
Uma variante do widget Entry, usada para selecionar um número fixo de valores.

### 🪟 PanedWindow
Widget de contêiner que pode conter qualquer número de painéis, organizados **horizontalmente** ou **verticalmente**.

### 📦 LabelFrame
Widget de contêiner simples, usado principalmente como espaçador ou para agrupar widgets em um layout.

### ⚠️ tkMessageBox
Módulo usado para exibir caixas de mensagens.

---

## ✅ Observações
- Os widgets são os elementos fundamentais para construir interfaces gráficas no Tkinter.  
- Podem ser organizados em **frames**, janelas (`Toplevel`) e configurados com **geometria (pack, grid, place)**.

# Exemplos de Aplicações GUI em Python com Tkinter

Este projeto apresenta exemplos práticos de desenvolvimento de **interfaces gráficas de usuário (GUI)** em Python utilizando a biblioteca **Tkinter**. Cada exemplo mostra como usar um widget diferente, permitindo criar aplicações interativas.

---

## Pré-requisitos

* Python instalado (versão recomendada >= 3.8)
* Bibliotecas Tkinter e ttk (já inclusas na instalação padrão do Python)

---

## Widgets e Exemplos

### 1. Window (`tk.Tk()`)

Cria a janela principal da aplicação.

```python
import tkinter as tk
janela = tk.Tk()
janela.title("Aplicação GUI")
janela.resizable(False, False)  # Impede redimensionamento
janela.mainloop()
```

---

### 2. Label

Exibe textos na interface.

```python
from tkinter import ttk
ttk.Label(janela, text="Componente Label").grid(column=0, row=0)
```

---

### 3. Button

Botões executam ações quando clicados.

```python
import tkinter as tk
def fechar():
    janela.destroy()
tk.Button(janela, text='Fechar', command=fechar).pack()
```

---

### 4. Entry

Campo de entrada de dados pelo usuário.

```python
e1 = tk.Entry(janela)
e1.grid(row=0, column=1)
```

---

### 5. Radiobutton

Seleciona **uma opção entre várias**.

```python
v = tk.IntVar()
tk.Radiobutton(janela, text="Python", variable=v, value=1).pack(anchor=tk.W)
tk.Radiobutton(janela, text="C++", variable=v, value=2).pack(anchor=tk.W)
```

---

### 6. Checkbox

Permite selecionar **uma ou mais opções**.

```python
var1 = tk.IntVar()
ttk.Checkbutton(janela, text="Gerencial", variable=var1).grid(row=1, sticky=tk.W)
```

---

### 7. Text

Campo de texto multilinha.

```python
T = tk.Text(janela, height=2, width=30)
T.pack()
T.insert(tk.END, "Exemplo de texto\nem duas linhas")
```

---

### 8. Message

Exibe mensagens formatadas.

```python
msg = tk.Message(janela, text="Mensagem para o usuário")
msg.config(bg='lightgreen', font=('times', 24, 'italic'))
msg.pack()
```

---

### 9. Slider (`ttk.Scale`)

Escolhe valores em uma escala.

```python
from tkinter import ttk
w1 = ttk.Scale(janela, from_=0, to=50)
w1.pack()
```

---

### 10. Dialog (`messagebox`)

Caixas de diálogo interativas.

```python
from tkinter import messagebox as mb
mb.showerror("Erro", "Mensagem de erro")
```

---

### 11. Combobox

Caixa de seleção com opções pré-definidas.

```python
from tkinter import ttk
n = tk.StringVar()
escolha = ttk.Combobox(janela, textvariable=n)
escolha['values'] = ('Janeiro','Fevereiro','Março')
escolha.grid(row=0, column=0)
```

---

## Observações

* Teste cada widget separadamente antes de combiná-los.
* Widgets podem ser configurados com cores, fontes, tamanhos e comportamentos personalizados.
* Esses exemplos podem ser usados como base para formulários, calculadoras, contadores e projetos interativos.

---

## Autor

**Matheus** - Entusiasta de programação e desenvolvimento de interfaces GUI em Python.

