# Introdução à engenharia de prompts com o Copilot do GitHub

- Crie prompts eficazes que otimizam o desempenho do Copilot do GitHub, garantindo precisão e relevância em cada sugestão de código.
- Entenda a relação complexa entre prompts e respostas do Copilot e utilize as boas práticas da engenharia de prompts.
- Obtenha insights sobre o mecanismo subjacente à forma como o Copilot do GitHub lida com os prompts do usuário, desde a transmissão segura até a filtragem de conteúdo e à análise de contexto.


### Pré-requisitos

- Conhecimento básico de codificação.
- Acesso ao Copilot do GitHub: Para usá-lo, você pode instalar a extensão do Copilot do GitHub disponível para você nos seguintes Ambientes de Desenvolvimento Integrado (IDEs):
    - Visual Studio
    - Visual Studio Code
    - Neovim
    - IDEs da JetBrains (IntelliJ, PyCharm, WebStorm etc.)
- Uma conta do GitHub para conectar seu editor de código ao Copilot.


## Introdução

O GitHub Copilot, da plataforma OpenAI, está mudando o jogo no desenvolvimento de software. Não se trata apenas de uma ferramenta para sugerir códigos. O GitHub Copilot pode compreender os detalhes intrincados do seu projeto por meio do treinamento de dados que contêm linguagem natural e bilhões de linhas de código-fonte de fontes disponíveis publicamente, incluindo código em repositórios públicos do GitHub. Isso permite que o GitHub Copilot forneça a você sugestões mais contextualmente relevantes.

Mas, para aproveitar ao máximo o GitHub Copilot, você precisa conhecer os prompts. É dessa forma que você informa ao Copilot o que precisa. A qualidade do código que ele devolve depende muito da clareza e da precisão de seus prompts.

Então, como você pode usar o GitHub Copilot em todo o seu potencial? Este módulo mostra a você como! Ele orientará você sobre os detalhes da criação de prompts eficazes para obter as melhores sugestões de código, ajudando a codificar mais rápido e melhor.

## Fundamentos de engenharia e melhores práticas de prompts

- O que é engenharia de Prompts?
- Fundamentos da engenharia de Prompt
- Melhores práticas na engenharia de Prompts
- Como o Copilot aprende com seus Prompts

### Princípios da engenharia de Prompt


- Único: Sempre foque seu prompt em uma tarefa ou pergunta única e bem definida. Essa clareza é fundamental para obter respostas precisas e úteis do Copilot.
- Específico: Certifique-se de que suas instruções sejam explícitas e detalhadas. A especificidade leva para sugestões de código mais aplicáveis e precisas.
- Curto: Ao ser específico, mantenha os prompts concisos e diretos. Esse equilíbrio garante clareza sem sobrecarregar o Copilot ou complicar a interação.
- Contextual: Utilize nomes de arquivos com descrição e mantenha os arquivos relacionados abertos. Isso fornece ao Copilot um contexto avançado, levando para sugestões de código mais personalizadas.

#### Forneça clareza suficiente

![image-20240614212839767](/home/dop/.config/Typora/typora-user-images/image-20240614212839767.png)

#### Fornecer contexto suficiente com detalhes

![image-20240614213038567](/home/dop/.config/Typora/typora-user-images/image-20240614213038567.png)

#### Fornecer exemplos para aprendizado

![image-20240614213121249](/home/dop/.config/Typora/typora-user-images/image-20240614213121249.png)

#### Aprendizado Zero-shot

![image-20240614213214536](/home/dop/.config/Typora/typora-user-images/image-20240614213214536.png)

#### Aprendizado One-shot

![image-20240614213315808](/home/dop/.config/Typora/typora-user-images/image-20240614213315808.png)

#### Few-shot learning

![image-20240614213351252](/home/dop/.config/Typora/typora-user-images/image-20240614213351252.png)

### Fluxo do processo de prompts do usuário do GitHub Copilot
#### Processar

### 1. Transmissão segura de prompts e coleta de contexto

O processo começa com a transmissão segura do prompt do usuário por  HTTPS. Isso garante que seu comentário em linguagem natural seja enviado aos servidores do GitHub Copilot de forma segura e confidencial,  protegendo as informações confidenciais.

O GitHub Copilot recebe com segurança o prompt do usuário, que pode  ser um chat do Copilot ou um comentário em linguagem natural fornecido  por você no seu código.

Simultaneamente, o Copilot coleta detalhes de contexto:

- O código antes e depois da posição do cursor, o que o ajuda a entender o contexto imediato do prompt.
- O nome e tipo do arquivo que está sendo editado, permitindo que adapte sugestões de código ao tipo de arquivo específico.
- Informações sobre as guias abertas adjacentes, garantindo que o  código gerado se alinhe a outros segmentos de código no mesmo projeto.

### 2. Filtragem de conteúdo

O Copilot incorpora mecanismos de filtragem de conteúdo antes de  prosseguir com a extração de intenções e geração de código, para  garantir que as respostas e o código gerado não incluam nem promovam:

- **Dados pessoais**: O Copilot filtra o conteúdo de modo a deixar de fora todos os dados pessoais, como nomes, endereços ou  números de identidade, para proteger a privacidade e a segurança de  dados do usuário.
- **Discurso de ódio e conteúdo inadequado**: O Copilot  usa algoritmos para detectar e impedir a geração de discursos de ódio,  linguagem ofensiva ou um conteúdo inadequado que possa ser prejudicial  ou ofensivo.

### 3. Análise de contexto

Após a filtragem de conteúdo, o Copilot usa as informações de  contexto coletadas, incluindo snippets de código e tipos de arquivo,  para contextualizar o prompt do usuário. Esse contexto abrangente ajuda o Copilot a entender a relevância do prompt e a tarefa de codificação que supostamente deve abordar. O Copilot entende o contexto e executa o  seguinte:

- **Extração da intenção**: O Copilot prossegue para  extrair sua intenção do comentário em linguagem natural. Identifica  palavras-chave, frases e indicações de contexto dentro do prompt.
- **Mapeamento da intenção**: O Copilot mapeia a intenção extraída para ações ou funcionalidades de codificação específicas,  levando em conta o conteúdo do prompt e as informações contextuais. Essa etapa converte a solicitação de alto nível do usuário em uma tarefa de  codificação concreta.

### 4. Geração de código

Baseando-se na intenção mapeada, o Copilot executa as seguintes ações:

- Fornece sugestões de código adaptadas às suas preferências de código.
- Sugere nomes de funções e variáveis apropriados.
- Elabora blocos de código completos, garantindo a precisão da sintaxe e do contexto.
- Alinha-se à linguagem, à estrutura e aos padrões específicos do projeto.
- Respeita configurações personalizadas, como estilos e restrições de codificação.

### 5. Interação do usuário

O Copilot lhe apresenta o código gerado para você revisar e interagir, com as seguintes opções:

- Aceitar o código como está.
- Fazer modificações no código sugerido.
- Rejeitar as sugestões de código.

### 6. Início do loop de feedback

O Copilot inicia um loop de feedback com base nas suas ações com os seguintes objetivos:

- Aumentar seu próprio conhecimento com base nas sugestões aceitas.
- Aprender e se aprimorar por meio de modificações e rejeições das sugestões.

### 7 - Repetir para os prompts subsequentes

O processo é repetido à medida que você fornece mais prompts, com o  Copilot lidando continuamente com as solicitações do usuário, entendendo sua intenção e gerando um código como resposta. Com o tempo, o Copilot  aplica os dados cumulativos de feedback e de interação, incluindo os  detalhes de contexto, para aprimorar seu entendimento da intenção do  usuário e refinar seus recursos de geração de código.

### Modelos de Linguagem Grande (LLMs) do GitHub Copilot

## LLMs de ajuste fino

O ajuste fino é um processo crucial que nos permite adaptar Modelos  de Linguagem Grande (LLMs) pré-treinados para tarefas ou domínios  específicos. Envolve o treinamento do modelo em um conjunto de dados  menor e específico por tarefa — conhecido como conjunto de dados de  destino — e, ao mesmo tempo, o uso do conhecimento e dos parâmetros  obtidos de um conjunto de dados grandes pré-treinado — conhecido como  modelo de origem.

![image-20240614213808514](/home/dop/.config/Typora/typora-user-images/image-20240614213808514.png)

### Ajuste fino LoRA

Realizar um ajuste fino total tradicional significa treinar todas as  partes de uma rede neural, um processo que pode ser lento e fortemente  dependente de recursos. Mas o ajuste fino de LoRA (Learning to Rank ou,  em português, aprender a classificar) é uma alternativa inteligente. A  técnica é usada para fazer com que modelos de linguagem grandes (LLMs)  pré-treinados funcionem melhor para tarefas específicas sem precisar  refazer todo o treinamento.

Veja como o LoRA funciona:

- Em vez de mudar tudo, o LoRA adiciona partes treináveis menores a cada camada do modelo pré-treinado.
- O modelo original permanece o mesmo, o que economiza tempo e recursos.

Confira os melhores aspectos do LoRA:

- A técnica supera outros métodos de adaptação, como adaptadores e ajustes de prefixos.
- É como obter resultados excelentes com menos variáveis e imprevistos.

Em termos simples, o ajuste fino LoRA gira em torno de trabalhar de  forma mais inteligente, não mais difícil, para tornar os LLMs mais  adequados aos seus requisitos de codificação específicos ao usar o  Copilot.

### References

- [Dentro do GitHub: Trabalhando com as LLMs por trás do GitHub Copilot – O Blog do GitHub](https://github.blog/2023-05-17-inside-github-working-with-the-llms-behind-github-copilot/)
- [Como usar o GitHub Copilot: Prompts, dicas e casos de uso – Blog do GitHub](https://github.blog/2023-06-20-how-to-write-better-prompts-for-github-copilot/)

### Conquistas

![image-20240614214352090](/home/dop/.config/Typora/typora-user-images/image-20240614214352090.png)