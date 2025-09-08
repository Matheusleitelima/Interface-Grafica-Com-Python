# Formulário com Tkinter

O exemplo consiste em um formulário de inscrição com campos de **Nome** e **Email**, além de um botão para enviar os dados.

---

## 🚀 Passo a Passo

### 1. Recuperar os dados com `.get()`

```python
def submit():
    nome_valor = entry_nome.get()
    email_valor = entry_email.get()

    print("Nome:", nome_valor)
    print("Email:", email_valor)
```

---

### 2. Criar a janela principal

```python
root = tk.Tk()
root.title("Formulário de Inscrição")
```

---

### 3. Criar um frame (área onde os widgets ficam organizados)

```python
frame = tk.Frame(root)
frame.pack(padx=10, pady=10)  # distância da borda
```

---

### 4. Campo de entrada Nome

```python
entry_nome = tk.Entry(frame)
entry_nome.grid(row=0, column=1)  # Linha 0, coluna 1
```

---

### 5. Campo de entrada Email

```python
entry_email = tk.Entry(frame)
entry_email.grid(row=1, column=1)  # Linha 1, coluna 1
```

---

### 6. Botão para enviar os dados

```python
submit_button = tk.Button(frame, text="Submeter", command=submit)
submit_button.grid(row=2, columnspan=2, pady=10)
```

---

### 7. Inicializar a interface (loop principal)

```python
root.mainloop()
```

---

## 📌 Código Completo

```python
import tkinter as tk

def submit():
    nome_valor = entry_nome.get()
    email_valor = entry_email.get()

    print("Nome:", nome_valor)
    print("Email:", email_valor)

# Criar janela principal
root = tk.Tk()
root.title("Formulário de Inscrição")

# Criar frame
frame = tk.Frame(root)
frame.pack(padx=10, pady=10)

# Campo Nome
tk.Label(frame, text="Nome:").grid(row=0, column=0, padx=5, pady=5)
entry_nome = tk.Entry(frame)
entry_nome.grid(row=0, column=1)

# Campo Email
tk.Label(frame, text="Email:").grid(row=1, column=0, padx=5, pady=5)
entry_email = tk.Entry(frame)
entry_email.grid(row=1, column=1)

# Botão
submit_button = tk.Button(frame, text="Submeter", command=submit)
submit_button.grid(row=2, columnspan=2, pady=10)

# Loop principal
root.mainloop()
```

---

## 🖼️ Resultado esperado

- Uma janela chamada **Formulário de Inscrição**.  
- Dois campos de texto: **Nome** e **Email**.  
- Um botão **Submeter**, que ao clicar imprime no terminal os valores digitados.

---

## ✅ Observações

- Sempre evite nomear seus arquivos como `tkinter.py`, pois isso conflita com a biblioteca original.  
- Você pode expandir esse projeto para salvar os dados em um arquivo `.txt`, banco de dados ou exibi-los na própria interface.  
