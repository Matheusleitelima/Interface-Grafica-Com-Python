# Interface Gráfica com Python (GUI)

## Conceitos importantes

* **GUI (Graphical User Interface)**: Interface gráfica que permite interação do usuário com aplicativos.
* **Frameworks**: Ferramentas que facilitam a criação de interfaces gráficas.
* **Experiência do usuário (UX)**: Foco na facilidade e na interação da aplicação com quem usa.

## Comparação de Frameworks

| Framework         | Principais características                                                        | Uso recomendado                                                |
| ----------------- | --------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| **Tkinter**       | Padrão do Python, leve, fácil de aprender                                         | Ideal para iniciantes e aplicações simples                     |
| **PyQt / PySide** | Robusto, permite criar GUIs complexas, comercialmente viável                      | Aplicações profissionais e complexas                           |
| **Kivy**          | Multiplataforma (Windows, Linux, macOS, Android, iOS), escrito em Python e Cython | Apps móveis e desktop que precisam rodar em várias plataformas |
| **Flexx**         | Baseado em tecnologia web (HTML, CSS, JS), roda no navegador                      | Aplicações GUI modernas com base web                           |
| **CEF Python**    | Embute o Chrome em Python, permite criar apps baseados em navegador               | Apps que precisam usar Chromium internamente                   |
| **PyForms**       | Suporta web, terminal, desktop GUI, fácil de criar formulários                    | Ferramentas administrativas e protótipos rápidos               |
| **wxPython**      | Framework tradicional, multiplataforma                                            | Aplicações desktop nativas                                     |
| **PyAutoGUI**     | Controla mouse e teclado, ideal para automação e testes de interface              | Testes automatizados ou bots de interação com a GUI            |
| **PySimpleGUI**   | Simplifica a criação de GUI, baseado em Tkinter, Qt ou Remi                       | Aplicações rápidas e simples, prototipagem                     |

## Exemplos e testes

### Tkinter

```bash
pip install tkinter
```

```python
import tkinter
tkinter._test()
```

### PyQt5

```bash
pip install PyQt5
```

```python
import sys
from PyQt5 import QtCore, QtWidgets
from PyQt5.QtWidgets import QMainWindow, QLabel, QGridLayout, QWidget
from PyQt5.QtCore import QSize

class HelloWindow(QMainWindow):
    def __init__(self):
        super().__init__()
        self.setMinimumSize(QSize(280, 120))
        self.setWindowTitle("Olá, Mundo! Exemplo PyQt5")
        centralWidget = QWidget(self)
        self.setCentralWidget(centralWidget)
        gridLayout = QGridLayout(self)
        centralWidget.setLayout(gridLayout)
        title = QLabel("Olá Mundo para PyQt", self)
        title.setAlignment(QtCore.Qt.AlignCenter)
        gridLayout.addWidget(title, 0, 0)

if __name__ == "__main__":
    app = QtWidgets.QApplication(sys.argv)
    mainWin = HelloWindow()
    mainWin.show()
    sys.exit(app.exec_())
```

### Kivy

```bash
pip install Kivy
```

```python
from kivy.app import App
from kivy.uix.label import Label

class MeuApp(App):
    def build(self):
        return Label(text="Olá, Matheus! 🚀\nSeu Kivy está funcionando!")

if __name__ == "__main__":
    MeuApp().run()
```

### Flexx

```bash
pip install flexx
```

```python
from flexx import flx

class Exemplo(flx.Widget):
    def init(self):
        flx.Button(text='Olá')
        flx.Button(text='Mundo')

if __name__ == '__main__':
    a = flx.App(Exemplo, title='Flexx demonstração')
    a.launch()
    flx.run()
```

### CEF Python

```bash
pip install cefpython3
```

```python
from cefpython3 import cefpython as cef
import platform
import sys

def main():
    check_versions()
    sys.excepthook = cef.ExceptHook
    cef.Initialize()
    cef.CreateBrowserSync(
        url="https://www.google.com/",
        window_title="Olá, mundo! Este é o primeiro exemplo do CEF python"
    )
    cef.MessageLoop()
    cef.Shutdown()

def check_versions():
    ver = cef.GetVersion()
    print(f"[hello_world.py] CEF python {ver['version']}")
    print(f"[hello_world.py] Chromium {ver['chrome_version']}")
    print(f"[hello_world.py] CEF {ver['cef_version']}")
    print(f"[hello_world.py] Python {platform.python_version()} {platform.architecture()[0]}")
    assert cef.__version__ >= "57.0", "CEF python v57.0+ required to run this"

if __name__ == '__main__':
    main()
```

### PyForms

```bash
pip install pyforms
```

```python
import pyforms
from pyforms.basewidget import BaseWidget
from pyforms.controls import ControlText, ControlButton

class ExemploSimples(BaseWidget):
    def __init__(self):
        super().__init__('Exemplo Simples')
        self._nome = ControlText('Nome', 'Default value')
        self._sobrenome = ControlText('Sobrenome')
        self._nomeCompleto = ControlText('Nome completo')
        self._button = ControlButton('Pressione o Botão')
        self._button.value = self.botao_clicado

    def botao_clicado(self):
        self._nomeCompleto.value = f"{self._nome.value} {self._sobrenome.value}"

if __name__ == "__main__":
    from pyforms import start_app
    start_app(ExemploSimples)
```

### wxPython

```bash
pip install wxpython
```

```python
import wx

class Janela(wx.Frame):
    def __init__(self, parent, title):
        super().__init__(parent, title=title, size=(400,300))
        self.panel = wx.Panel(self)
        self.text_ctrl = wx.TextCtrl(self.panel, pos=(5,5))
        self.btn_test = wx.Button(self.panel, label='Pressione esse componente!', pos=(5,55))

class ExemploApp(wx.App):
    def OnInit(self):
        self.frame = Janela(None, "Janela wxPython")
        self.frame.Show()
        return True

app = ExemploApp()
app.MainLoop()
```

### PyAutoGUI

```bash
pip install pyautogui
```

```python
import pyautogui
pyautogui.moveTo(100, 150)
pyautogui.click()
pyautogui.write('Olá, Mundo!', interval=0.25)
pyautogui.alert('Esta é a mensagem para Tela.')
```

### PySimpleGUI

```bash
pip install PySimpleGUI
```

```python
import PySimpleGUI as sg
sg.theme('DarkAmber')

layout = [
    [sg.Text('Texto na linha 1')],
    [sg.Text('Entre com um texto na linha 2'), sg.InputText()],
    [sg.Button('Ok'), sg.Button('Cancel')]
]

window = sg.Window('Bem-Vindo ao PySimpleGUI', layout)

while True:
    event, values = window.read()
    if event == sg.WIN_CLOSED or event == 'Cancel':
        break
    print('Você entrou com:', values[0])

window.close()
```

## Vantagens e desvantagens gerais

* **Vantagem**: Melhor interação com o usuário, aplicações visuais e intuitivas.
* **Desvantagem**: Maior consumo de recursos, exige atenção ao design e à lógica da GUI.
