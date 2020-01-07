---
layout: post
title: "Usando os pull requests a favor do seu time"
date: 2020-01-02
excerpt: "Um texto com algumas dicas para deixar o momento do pull request mais amigável."
tags: [pull request, git, github, workflow]
comments: false
---

![Imagem da internet com o workflow do GitHub](https://cdn-images-1.medium.com/max/800/0*K8P35YttgYS3TrU1)

Você chega em uma equipe, começa a utilizar o Git e chega o grande momento: revisar o pull request (PR) de alguém ou submeter um PR para revisão. O que esperar nesse momento? Muitos comentários? Quanto menos comentários melhor? Isso pode ser assustador.

Em algumas equipes a revisão de PRs podem gerar momentos tensos, cheios de tretas. Ninguém gosta de ser criticado, mas quando há algo errado no código, ele precisa ser trazido à tona. Nem sempre é fácil aceitar críticas de algo que você fez com tanto carinho ou que para você foi a melhor forma de fazer. Também pode não ser fácil falar com a pessoa autora do PR que há formas melhores de fazer algo.

Estava numa equipe em que as revisões de PRs eram estressantes e sempre tinha alguém que iria fazer algum comentário passivo-agressivo. Fiz uma pesquisa e encontrei um artigo chamado [“Performing a PR review”](https://dev.to/dijitalmunky/performing-a-pr-review) escrito por Chris Roe. Compartilhei com a equipe e todos gostaram. Chris cita 4 princípios que ele tem em mente ao revisar um PR, estes princípios ajudam o processo a ser mais suave, não importa se você é o revisor ou o autor.

### Princípio 1 — Seja flexível

![GIF em que dois homens levantam um contorcionista pelos braços e pelas pernas](https://cdn-images-1.medium.com/max/800/0*oOZZY9VnJilmSbZs)

Vá para a revisão do PR com a mente aberta. Codificar é arte, mas também é ciência. Precisamos aprender que correção técnica não necessariamente é equivalente a um bom código. Exemplo simples: adianta todas as variáveis do código estarem nomeadas corretamente se o código for lento e frustrar o usuário?

Chris cita o exemplo de um desenvolvedor que estava tão focado em escrever um bom código com um ORM que achava incrível. O problema era que esse era um processo em lote que precisava copiar gigabytes de dados de um banco de dados para outro. O uso de um ORM transacional era basicamente uma abordagem repleta de problemas, pois precisava carregar cada registro em um objeto para transferi-lo. Uma abordagem alternativa teria usado uma ferramenta de transferência em massa para transmitir os dados entre os bancos de dados e minimizar a sobrecarga de memória. No entanto, esse desenvolvedor estava tão convencido de que como seu código elegante era perfeito, não conseguiu enxergar além da correção técnica para o problema atual, por isso foi para a produção. Logo, começamos a ver problemas de memória à medida que os conjuntos de dados aumentavam e o processo começava a falhar…

Lembre-se também que todos nós temos maneiras diferentes de abordar problemas e diferentes estilos de codificação. No final, se houver vários estilos na base de código, será que realmente importa se os mantenedores puderem entender o código? Por exemplo, realmente importa que você perdeu um sublinhado à esquerda em uma variável de instância se o resto do nome for intuitivo para a equipe? Ou será que realmente importa se as chaves {} estão na mesma linha que a declaração do método ou na linha seguinte? O código ainda compila e executa da mesma forma, independentemente…

### Princípio 2 — Seja curioso

![GIF de um gato sob as duas patas traseiras tentando enxergar algo que esta longe](https://cdn-images-1.medium.com/max/800/0*u0lETO6EHgRcwGDe)

Veja o processo de revisão do PR como uma oportunidade de aprendizado. Ambos os lados do PR têm a oportunidade de aprender. Em vez de ser crítico e dizer algo como:

> “Isso está errado porque X"

faça uma pergunta como:

> “Essa é uma abordagem interessante, o que o levou a seguir esse caminho?”

Você também pode dar mais um passo e adicionar uma sugestão se realmente acha que algo está quebrado. Por exemplo:

> “Sua lógica para processar esta coleção é agradável, simples e sólida. Pergunto-me, no entanto, se podemos melhorá-la usando o novo método de coleção `_.ForEach()_` para que o mecanismo de tempo de execução possa otimizar e processar a coleção em paralelo ou multi-threaded?”

Fazer as coisas dessa maneira dá crédito ao que a pessoa fez e faz perguntas abertas para iniciar o diálogo sobre como as coisas podem ser melhoradas.

### Princípio 3 — Não é pessoal

![GIF de uma menina revirando os olhos](https://cdn-images-1.medium.com/max/800/0*ndxHIQNkel1Ep9r8)

Ao trabalhar em equipe, é importante que todos percebam que o código é apenas código. Tente não tratá-lo como uma extensão do autor (você ou os outros), embora seja lógico se sentir assim (alguém o escreveu afinal, usando seus próprios cérebros e idéias, então há uma quantidade de reflexão de si mesmo ali). No entanto, esses sentimentos precisam vir em segundo lugar para o objetivo da equipe e o objetivo do código. Por exemplo, eu posso me orgulhar de um truque inteligente no meu código, ou o que eu acho que é uma maneira particularmente elegante de escrever algo. No entanto, se esse código for difícil de manter para outros, ou for muito lento para um usuário final, provavelmente precisará ser alterado. Eu encontrei com demasiada frequência desenvolvedores que medem a auto-estima pelo que os outros pensam sobre o seu código. Pensar dessa maneira pode ser verdadeiramente devastador para todos os envolvidos. Faça um favor a si mesmo e descubra como passar o código sendo “seu”. As pessoas irão lhe abordam mais facilmente e livremente.

### Princípio 4 — Não esqueça o elemento humano

![GIF onde um homem toca na tela, dando a entender que esta querendo tocar o leitor](https://cdn-images-1.medium.com/max/800/0*MGVmn5c39D4MsoAM)

Muitas vezes colocamos a tecnologia entre nós e os outros. Enviar mensagens de texto em vez de conversar pessoalmente ou fazer uma ligação telefônica é um exemplo disso. Não me entenda mal, mensagens de texto e sistemas de bate-papo como o Slack são incríveis e trazem enormes benefícios, mas muitas vezes esquecemos suas limitações e desvantagens. As pessoas são animais inerentemente sociais e inerentemente se comportam de maneira diferente em situações próximas ao rosto.

Outro bom exemplo, no contexto de PRs e revisões de código, é que muitos sistemas git (Github, BitBucket, Gitlab) permitem que comentários sejam colocados em e através de PRs. Isso, no entanto, pode causar problemas, porque esses sistemas removem as análises face a face e os PRs são essencialmente sobre “verificar o trabalho de alguém”. Muita comunicação não-verbal e outras sugestões sociais são perdidas quando você só usa esses sistemas. Não me entenda mal, coisas como essa são úteis e têm seu propósito, não podemos esquecer que somos seres sociais. Eu sugiro conhecer seu público e ajustar (_veja o Princípio 1: Seja flexível)_. Há pessoas que estão bem apenas com o uso deste sistema de comunicação, uma vez que não se ofendem se algo pode ser feito não como pretendido. No entanto, na mesma equipe, pode ter pessoas para as quais isso não funciona muito bem. É importante saber o que funciona para diferentes colegas de equipe e ajustar. Quando não temos certeza de como um colega de equipe provavelmente reage podemos fazer o seguinte:

-   Usar o sistema de comentários como uma maneira de marcar problemas, incluindo uma breve descrição do problema _(ótima oportunidade para aplicar fortemente o Princípio 2 ao escrever essas descrições)_. Isto é simplesmente para que nada seja esquecido e para que ambos possamos encontrar o código afetado rapidamente. Nada mais
-   Ao fazer a revisão, sentar com a pessoa, pessoalmente ou ao telefone, e passar onde estão as preocupações no PR. Não é simplesmente ler os comentários do PR para a pessoa mas dialogar sobre os comentários. O Princípio 2 pode ser muito útil aqui e ajudar nessa conversa.

### Resumindo…

Ao revisar um pull request ou ao criar um, devemos ser humildes e ter em mente que esta é uma oportunidade de aprendizado.

Não seja um idiota!

![GIF demonstrado uma equipe unida](https://cdn-images-1.medium.com/max/800/0*1NdJg57kapAnPsY4)
