# imers-o-alura-IA
# ✨ Olha só: O Agente que Dá Voz e Alma às Fotos! ✨

Olá! Seja muito bem-vindo(a) ao projeto "Olha só", onde a Inteligência Artificial encontra a inclusão de um jeito super especial. 😄

Fiz um video para você ter mais informações sobre o projeto: https://youtube.com/shorts/q5tZZpV_ho8 

## 🤩 Qual é a Grande Ideia?

Sabe aquela foto linda que você tirou ou aquela imagem que chegou no grupo da família? Ou ainda uma foto em um museu ou exposição que você esta visitando naquele momento? E se você não pudesse *vê-la*? Pois é! O "Olha só" nasce com um coração gigante para ajudar **pessoas cegas e com baixa visão** a também a se conectar a essas imagens.

Nosso objetivo é transformar a visualização de fotos em uma experiência auditiva completa e envolvente! Chega de barreiras na comunicação visual! Com o "Olha só", uma foto se transforma em uma audiodescrição detalhada e empolgante, permitindo que todos "vejam" e interajam com o mundo das imagens de uma forma mais fluida e autônoma. É a comunicação sem limites, turbinada pela IA! 😎

## 🤩 Como nasceu a Ideia?

Sou casado com a Cintia, que além de ser diretora teatral, dramaturga e roteirista, também é audiodescritora. Eu estava querendo fazer um projeto envolvendo leitura de imagens e geração de conteúdo com base nessa técnica, pois também sou fotografo. Ela então me deu a dica de usar os agentes para leitura e audiodescrição para ajudar nossos amigos cegos e com baixa visão a ter uma vida com maior acesso e autonomia. No final, meu enteado Pedro deu o  nome "Olha só", que além de ter tudo a ver com a dinamica dos agentes, também enfatiza a questão da independencia. 

## 🤖 Conheça a Turma de Agentes!

Nosso projeto possui muitos agentes super dedicados, cada um com uma missão vital para que tudo aconteça de forma fluída e rápida:

1.  📸 **Agente de Importação de Fotos:** O pontapé inicial! Ele é o responsável por receber a foto que você quer que seja descrita. Pense nele como o porteiro digital que abre as portas para a imagem entrar no nosso sistema.
2.  ✍️ **Agente Gerador de Descrição (Texto):** Esse é o nosso poeta visual! Utilizando o poder do Google Gemini, ele olha a foto (com olhos de IA, claro!) e transforma tudo que vê em um texto rico em detalhes, cores, ações e emoções. É como se a foto contasse a própria história, escrita por um super-narrador!
3.  🎙️ **Agente Gerador de Áudio (MP3):** E para completar a festa, temos o dublador oficial! Ele pega o texto gerado pelo Agente 2 e o transforma em um arquivo de áudio MP3 claro e agradável de ouvir. Assim, a descrição da foto chega aos ouvidos de forma acessível em qualquer hora e lugar!

Juntos, eles formam uma orquestra de IA que harmoniza imagem, texto e som para criar uma experiência inclusiva e fantástica!

## 🚀 Bora Colocar pra Rodar!

Este projeto foi desenvolvido em um ambiente de notebook (como o Google Colab), o que facilita muito a experimentação! Para testar e validar essa aplicação, siga os passos simples abaixo:

### Pré-requisitos

* Uma conta Google.
* Acesso ao Google Colab (ou um ambiente Python com suporte a notebooks).
* Uma chave de API para o Google Gemini.

### Obtendo sua API Key do Google Gemini

Para que nossos Agentes possam *ver* e *descrever*, eles precisam da permissão para usar o modelo Gemini. Você pode obter sua chave de API gratuitamente (dentro dos limites de uso) seguindo os passos em:

* **Google AI Studio:** [https://aistudio.google.com/](https://aistudio.google.com/)
* Crie uma chave de API e guarde-a em segurança!

### Configurando o Ambiente e Instalando as Bibliotecas

O código que você forneceu já contém os comandos para configurar o ambiente no Google Colab. É super simples!

1.  Abra um novo notebook no Google Colab.
2.  Copie e cole **TODO** o código fornecido por você em uma célula.
3.  **Configurando a API Key no Colab:** O código usa `userdata.get('GOOGLE_API_KEY')`. No Google Colab, vá em `🔑` (ícone de chave) no menu da esquerda, clique em `Gerenciar secrets`. Adicione um novo Secret com o nome `GOOGLE_API_KEY` e cole o valor da sua chave de API que você obteve no Google AI Studio. Isso mantém sua chave segura e fora do código diretamente.
4.  **Executando as Células:** Rode as células do notebook sequencialmente. Os comandos `!pip install` irão instalar todas as bibliotecas necessárias:

    ```bash
    !pip install -q google-genai
    !pip install -q google-adk
    !pip install Pillow transformers torch torchvision torchaudio google-cloud-aiplatform google-generativeai
    !pip install gTTS Pillow
    ```
    *(Esses comandos estão presentes no código fornecido e serão executados automaticamente)*

### Entendendo o Código (As Etapas da Aula!)

O código reflete exatamente as etapas que aprendemos para construir agentes e utilizar modelos multimodais:

1.  **Configuração da API:** As primeiras linhas configuram o acesso ao Google Gemini usando sua chave de API.
2.  **Instalação de Ferramentas/Bibliotecas:** Os comandos `!pip install` garantem que todas as dependências (para agentes, processamento de imagem, síntese de voz, etc.) estejam presentes.
3.  **Definição dos Agentes/Funções:** O código estrutura a lógica em funções claras:
    * `carregar_e_exibir_imagem()`: Representa o **Agente de Importação**, interagindo com o sistema de arquivos para obter a imagem.
    * `gerar_audiodescricao_da_imagem()`: Representa o **Agente Gerador de Descrição**, usando o modelo Gemini Vision (`gemini-1.5-flash-latest` no código) para analisar a imagem com base em um `prompt` detalhado e gerar o texto.
    * `gerar_audio_da_descricao()`: Representa o **Agente Gerador de Áudio**, utilizando a biblioteca `gTTS` para converter o texto em fala e salvar como MP3.
4.  **Orquestração (`main()`):** A função `main()` coordena a sequência de execução: chama a função de carregar imagem, depois a de gerar descrição com o texto e a imagem, e por fim, opcionalmente, a de gerar o áudio.

É um exemplo prático de como combinar diferentes funcionalidades (importação, visão computacional, processamento de linguagem natural, síntese de voz) para criar uma aplicação útil e inclusiva, utilizando o conceito de agentes e modelos generativos!

## 🏃‍♀️ Como Usar (No Colab)

1.  Após rodar as células de configuração e instalação, rode a célula que contém a função `main()` e a chamada a ela.
2.  Quando solicitado, **carregue a imagem** que você deseja audiodescrever. Uma janela de upload do Colab aparecerá.
3.  Aguarde um pouquinho! O agente de descrição estará trabalhando.
4.  O texto da audiodescrição será exibido na tela. Leia com atenção!
5.  Você será perguntado se deseja gerar o áudio. Digite `s` e aperte Enter para ouvir a descrição falada, ou `n` para pular.
6.  Se escolher gerar o áudio, ele será reproduzido diretamente no notebook! ✨

## 💡 Próximos Passos!

Este é apenas o começo! O potencial do "Olha só" é enorme. Algumas ideias para o futuro:

* Permitir gerar descrição expandida, colocando informações extras sobre a foto, como exemplo: uma foto tirarda num museu mostrará uma descrição do autor da obra e a motivação e momento histórico que ela foi feita, com base em buscas qualificadas na web.
* Criar uma interface mais amigável (uma web app e mobile).
* Permitir a descrição de múltiplos objetos em uma cena com interação (perguntar sobre um item específico).
* Adicionar suporte a mais idiomas.
* Integrar com assistentes de voz.
* Gerar descrições em diferentes estilos (mais formal, mais divertido, para crianças, para idosos, para pessoas com espectro autista, inclusão de fundo musical etc.).
* Permitir interação contínua para refinar a descrição.

Se você tiver alguma ideia, junte-se a nós!

## 👋 Contribuições

Curtiu a ideia? Quer ajudar a tornar o "Olha só" ainda mais incrível? Suas contribuições são super bem-vindas! Sinta-se à vontade para:

* Abrir Issues para relatar bugs ou sugerir novas funcionalidades.
* Enviar Pull Requests com suas melhorias no código.

Toda ajuda é um passo a mais para um mundo mais acessível!

## 📬 Contato

Tem dúvidas, sugestões, ou só quer bater um papo sobre IA e inclusão? Me mande um oi!

[Geraldo de Lima]
[geralima09]
[geralima09@gmail.com]

---

**Um agradecimento especial aos professores da Imersão IA Alura + Google Gemini por compartilhar o conhecimento que tornou este projeto possível!**

