<h1 align="center"> :books:👩‍💻 Branches no Git 👩‍💻:books: </h1><br/>

Quase todo Sistema de Controle de Versionamento tem alguma forma de suporte a ramificações (Branches). Ramificação significa que você diverge da linha principal de desenvolvimento e continua a trabalhar sem alterar essa linha principal. Em muitas ferramentas versionamento, este é um processo um tanto difícil, geralmente exigindo que você crie uma nova cópia do diretório do código-fonte, o que pode demorar muito em projetos maiores.

Algumas pessoas se referem ao modelo de ramificação do Git como seu “recurso matador” e certamente diferencia o Git na comunidade de sistemas de versionamento. Por que isso é tão especial? A forma como o Git cria branches é incrivelmente leve, tornando as operações de ramificação quase instantâneas, alternando entre os branches geralmente com a mesma rapidez. Ao contrário de muitos outros sistemas, o Git incentiva fluxos de trabalho que se ramificam e se fundem com frequência, até mesmo várias vezes ao dia. Compreender e dominar esse recurso oferece uma ferramenta poderosa e única e pode mudar totalmente a maneira como você desenvolve.

***<h2> 📚 Branches em poucas palavras: </h2>*** 

Para realmente entender como o Git trabalha com Branches, precisamos dar um passo atrás e examinar como o Git armazena seus dados.

Como você deve se lembrar de << ch01-introdução >>, o Git não armazena dados como uma série de mudanças ou diferenças, mas sim como uma série de snapshots (instantâneos de um momento) .

Quando você faz um commit, o Git armazena um objeto de commit que contém um ponteiro para o snapshot do conteúdo que você testou. Este objeto também contém o nome do autor e o e-mail, a mensagem que você digitou e ponteiros para o commit ou commits que vieram antes desse commit (seu pai ou pais): sem pai para o commit inicial, um pai para um commit normal, e vários pais para um commit que resulta de uma fusão de dois ou mais branches.

Para verificar isso, vamos assumir que você tem um diretório contendo três arquivos, e você seleciona todos eles e efetua o commit. Ele Prepara os arquivos e calcula uma verificação para cada um (o hash SHA-1 que mencionamos em << ch01-introdução >>), armazena essa versão do arquivo no repositório Git (Git se refere a eles como blobs), e adiciona esse hash de verificação à área de preparação (staging area):



$ git add README test.rb LICENSE
$ git commit -m 'The initial commit of my project'



Quando você faz um commit executando `git commit`, o Git verifica cada subdiretório (neste caso, apenas o diretório raiz do projeto) e armazena esses objetos no repositório do Git. O Git então cria um objeto de commit que possui os metadados e um ponteiro para a raiz do projeto para que ele possa recriar aquele snapshots quando necessário.

Seu repositório Git agora contém cinco objetos: um blob para o conteúdo de cada um dos seus três arquivos, uma árvore que lista o conteúdo do diretório e especifica quais nomes de arquivo são armazenados e quais seus blobs e um commit com o ponteiro para essa árvore e todos os metadados de commit. :smile:


<h3 align="center"> {✿◠‿◠} Muita gratidão! ✨🤗✨<br/><h3>  

___
