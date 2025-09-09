# Study-KiviMD-KVLang
Nesse repositório, estudo KVLang, uma linguagem de programação, que com a biblioteca Python é possível criar aplicativos e softwares. Utilização de boas práticas, e código limpo. 

#Primeiros Passos
Etapa 1: Para utilizar o Kivi você deve abrir seu terminal, e digitar 

pip install kivy

Caso o Python não esteja certo, procure a versão mais recente, também busque atualizar o pip e retome a etapa 1

#Etapa 2: Criando meu primeiro software
Após a instalação você irá criar uma pasta, dentro dela dois arquivos distintos. Por exemplo

Aplicativo
  - main.py
  - MyApp.kv

Após a criação dos arquivos prosseguiremos com o código dentro do main.py, segue de exemplo um código básico: 

from kivy.app import import App 
from kivy.uix.boxlayout import BoxLayout
from kivy.uix.label import Label
from kivy.uix.button import Button

class LayoutApp(BoxLayout):
  def on_press_btn(self):
    janela.root_window.remove_widget(janela.root)
    janela.root_window.add_widget(LayoutApp2())

class LayoutApp2(BoxLayout):
  pass

class MyApp(App)
  def build(self)
    return LayoutApp()

janela=MyApp()
janela.run()

O que fizemos? primeiro chamamos a biblioteca kivy e suas funções mais básicas, que seria uma caixa de Layout, uma Label e um botão. Depois criamos um botão onde tem uma função de criar e remover janelas, em seguida criei a outra Janela que será exibida e em seguida, e sempre por ultimo, a classe MyApp que detem a função App da biblioteca Kivy. 

Importante a classe que detem a função App sempre precisa ter o mesmo nome que o arquivo KVlang, lembrando que o KVLang é uma linguagem mais "gráfica", seria como se fosse o CSS do HTML. 

Configurando o arquivo MyApp.kv

<LayoutApp>:
  BoxLayout:
    orientation: "vertical"
    Button:
      text: "Clique aqui"
      on_press: root.on_press_btn()
      size_hint: (0.5, 0.1)
      pos_hint: {"center_x":0.5, "center_y":0.5}

<LayoutApp2>:
   orientation: "vertical"
   BoxLayout:
     orientation: "vertical"
     Label:
       text: "Olá mundo!"
       pos_hint: {"center_x":0.5, "center_y":0.5}


Podemos observar que cada função de Layout do Python foi chamada da mesma forma no KVLang, não existe uma regra clara sobre, mas por boa prática e identificação utilizar as nomenclaturas irá facilitar o processo de identificar oque é cada função. 

#Outras funcionalidades

##Posicionamento e dimensão
A visualização precisa ser de um plano carteziano, onde o eixo X é a linha horizontal e o eixo Y é a linha vertical, sendo assim, conseguimos utilizar o pos_hint para dar as coordenadas da seguinte maneira: 

pos_hint: {"center_x":0.5, "center_y":0.5}

E se tratando de dimensão outras na documentação oficial do kivy, porém, a mais fácil é a size_hint, onde nela você ja dimensiona a largura e altura do objeto desse modo: 

size_hint: (0.5, 0.5)

Os valores do size_hint são decimais, então, 0.5 equivale a 50% da tela. 

O kivy possui FloatLayout, BoxLayout

##Layouts

Existem quatro formas de Layout, que é a BoxLayout, FloatLayout, StackLayout e a GridLayout

- BoxLayout organização em linha reta, horizontal e vertical
- FloatLayout organização é absoluta, e você utilizará o pos_hint e o size_hintpara ajuste de posição e tamanho relativo
- StackLayout forma pilhas, linhas a linha ou coluna em coluna
- GridLayout organiza através de linhas e colunas que os widgets se preenchem automáticamente

##Widgets

Existem muitos tipos de widgets, mas os mais comuns são as Labels, Button, TextInput. A declaração de todos pode ser vista nos primeiros passos na etapa 2. 

Outros widgets funcionais e importantes: 
- Image: inclusão de imagens dentro do aplicativo, seja dentro de botões, ou até mesmo avulso ao lado de labels
- Screenmanager: é um gerente de tela, muito util para um aplicativo que tem a necessidade de várias abas de tela
- CheckBox: uma caixa de check
- ButtonBehavior: seu nome já diz, ele é um botão escondido, tem capacidade para ser somente um texto estilo "clique aqui" ou um icone
        


