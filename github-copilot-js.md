# Usando o GitHub Copilot com JavaScript

## Introdução
### O que aprenderei?

- Configurar um repositório GitHub no Codespaces e instalar a extensão do GitHub Copilot.
- Prompts criados para gerar sugestões do GitHub Copilot
- GitHub Copilot aplicado para melhorar seus projetos.

### Pré-requisitos

Habilidades:

- Noções básicas sobre JavaScript e editores de texto.
- Compreensão básica dos conceitos básicos do Git e do GitHub e execução de comandos básicos `git` como `git add` e `git push`

## O que é o GitHub Copilot?

### Como funciona

```json
// Create a web API using express and JavaScript with routes for products and customers
```


  ```json
  const express = require(“express”);
  
  app = express();
  app.path(“/products”, () => “products”);
  app.listen(3000, () => “app runs”);
  ```

### Como configurar o GitHub Copilot

Para usar o GitHub Copilot, você precisa do seguinte:

Crie uma conta do GitHub – já que o Copilot é um serviço do GitHub, você precisa de uma conta do GitHub para usar o serviço.

Inscreva-se, você precisa se inscrever no Copilot por meio de sua página da Web.

No GitHub, selecione em seu perfil e vá para as configurações em que, no Copilot, você pode habilitar o acesso ou inscrever-se para uma avaliação gratuita.

Para usar o GitHub Copilot, você precisa instalá-lo como uma extensão em seu IDE.

As extensões estão disponíveis para IDEs principais, como o Visual Studio, Visual Studio Code.

## Exercício: Configurar o GitHub Copilot para trabalhar com o Visual Studio Code
### Configuração de ambiente

Primeiro, você precisa iniciar o ambiente do Codespaces, que vem pré-configurado com a extensão do GitHub Copilot.

1. Abra o [Codespace com o ambiente pré-configurado](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-javascript?quickstart=1) no navegador.
2. Na página **Criar codespace** , analise as definições de configuração do codespace e selecione **Criar novo codespace**
3. Aguarde até que o codespace seja iniciado. Esse processo de inicialização pode levar alguns minutos.
4. Os exercícios restantes neste projeto ocorrem no contexto desse contêiner de desenvolvimento.

## Usar o GitHub Copilot com JavaScript
### Engenharia de prompt

Embora o GitHub Copilot possa sugerir código à medida que você  digita, você também pode criar prompts para criar sugestões úteis. Um  prompt, que é a nossa entrada, é uma coleção de instruções ou diretrizes que ajudam a gerar o código. Um prompt é útil para gerar respostas  específicas a partir do Copilot. O prompt pode ser um comentário ou uma  entrada ao usar o GitHub Copilot Chat que orienta o Copilot a gerar  código em seu nome ou escrever código que o Copilot preenche  automaticamente.

A qualidade da saída do Copilot depende de quão bem você elabora seu  prompt. Portanto, projetar um prompt eficaz é crucial para garantir que  nós alcancemos os resultados desejados. Por exemplo, se você tiver o  prompt a seguir:

JavaScript 	

```javascript
// Create an API endpoint
```

Como o prompt é ambíguo e vago, o resultado do GitHub Copilot pode  não ser o que você precisa. Por exemplo, ele pode utilizar uma estrutura que você não conhece ou um ponto de extremidade que exige dados que  você não reconhece. No entanto, se você tiver o prompt a seguir:

JavaScript 	

```javascript
// Create an API endpoint using the React framework that accepts a JSON payload in a POST request
```

Esse último prompt é específico, claro e permite que o GitHub Copilot entenda o objetivo e o escopo da tarefa. Embora você também possa  fornecer contexto e exemplos para Copilot usando comentários ou código,  você também pode usar a opção de chat do GitHub Copilot Chat. Ter um bom prompt garante que o modelo gere uma saída de alta qualidade.

### Melhores práticas utilizando o GitHub Copilot

O Copilot aumenta muito sua produtividade, mas exige algumas boas  práticas para garantir a qualidade. Algumas das melhores práticas ao  usar o Copilot são:

Mantenha seus prompts simples e, em seguida, adicione componentes mais elaborados à medida que avança, por exemplo:

text 	

```text
create an HTML form with a text field and button
```

A seguir, elabore mais sobre o prompt para obter sugestões mais específicas:

text 	

```text
Add an event listen to the button to send a POST request to /generate endpoint and display response in a div with id "result"
```

Alterne entre as sugestões; você pode fazer isso utilizando `Ctrl+Enter` (ou `Cmd+Enter` em um Mac). Você receberá várias sugestões do Copilot e poderá escolher a melhor saída. Opcionalmente, ao usar o GitHub Copilot Chat, você pode usar a entrada de chat para adicionar seu prompt e interagir com a  saída.

Se estiver preso ou não estiver obtendo os resultados que você  deseja, poderá reformular o prompt ou começar a escrever código para o  Copilot preencher automaticamente.

## Exercício: Atualizar um portfólio do JavaScript com o GitHub Copilot
### Personalizar seu portfólio do JavaScript

Nesse portfólio de modelos, temos um aplicativo Web baseado em React  pronto para personalizar e implantar facilmente usando apenas seu  navegador da Web.

Antes de começar, você pode personalizar o portfólio com seus próprios links. Acesse `src/App.jsx` e atualize o `siteProps` com suas informações. A variável `siteProps` é um objeto JavaScript que contém pares de valores de chave usados para personalizar o site e deve ter essa aparência:

JavaScript 	

```javascript
const siteProps = {
  name: "Alexandrie Grenier",
  title: "Web Designer & Content Creator",
  email: "alex@example.com",
  gitHub: "microsoft",
  instagram: "microsoft",
  linkedIn: "satyanadella",
  medium: "",
  twitter: "microsoft",
  youTube: "Code",
};
```

### ## Animar seus ícones de mídia social com um prompt

Uma animação pode tornar a seção de redes sociais mais atraente. Peça a ajuda do Copilot para animar os ícones. Você pode usar o Chat do  GitHub Copilot para perguntar ao Copilot ou escrever o seguinte  comentário de prompt no arquivo `src/styles.css`:

css 	

```css
/* add an amazing animation to the social icons */
```

A sugestão do Copilot deve ser semelhante a essa:

css 	

```css
img.socialIcon:hover {
  animation: bounce 0.5s;
  animation-iteration-count: infinite;
}

@keyframes bounce {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.2);
  }
  100% {
    transform: scale(1);
  }
}
```

## 