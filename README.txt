//////////////////////IMAGEM FÁCIL-TRABALHO PRÁTICO DE IA\\\\\\\\\\\\\\\\\\\\\\\\\\\

Alunos: Richard Fernandes Pereira
Giovannini Barbosa
Henrique Teixeira
Gustavo Alves

O código fonte estará na pasta "src", na mesma pasta do agente. Lá estará um projeto do Netbeans IDE (compactado), e um arquivo .txt. Ambos contém o mesmo código, portanto caso o projeto não abra basta copiar e colar o conteúdo do .txt na sua IDE. O arquivo exe.cpp contém o código fonte do pequeno programa em C++ feito para "amarrar" as partes do programa, interpretar o input e tratar da limpeza após o término da execução. PARA COMPILAR E EXECUTAR O PROJETO PELA IDE, é necessário instalar a biblioteca Opencv para java, o que é algo muito complicado que não é descrito aqui (não tente pfv só execute pelo terminal mesmo).

////INPUT:
Basta colocar os links das paginas web desejadas dentro do arquivo t.txt, presente no mesmo diretório do programa em si.

---ATENÇÃO:
>Cada link deve ficar em uma linha diferente, e apenas um link por linha.
>Não há limite no número de links.
>NÃO RENOMEIE O ARQUIVO.
>Devido a limitações da ferramenta usada para baixar os prints das paginas web, algumas URLs podem não ser suportadas.
>O arquivo já vem com dois exemplos de sites que funcionam perfeitamente.

---PARÂMETROS:
É possível especificar dois parâmetros para o agente, o NÍVEL DE IGNORÂNCIA e DISTÂNCIA DAS IMAGENS
->Nivel de ignorância controla o limite do que o agente reconhece como "imagem". Quanto maior o nível, menos imagens serão reconhecidas (o agente irá 'ignorar' certos contornos). Deve ser modificado quando partes que não são imagens são reconhecidas junto. Os níveis vão de 1 a 5.
->Distância das images controla qual a distância mínima entre uma imagem e outra para que o agente reconheça cada individualmente, e não tudo como uma grande imagem. Com níveis maiores, imagens muito proximas irão "se fundir" em uma única imagem. Os níveis vão de 1 a 4.
>OS PARÂMETROS DEVEM SER ESCRITOS NA PRIMEIRA LINHA DO ARQUIVO t.txt, NIVEL DE IGNORANCIA PRIMEIRO, DISTANCIA DAS IMAGENS DEPOIS, COM UM ESPAÇO SEPARANDO AMBOS
->Por exemplo, o input:

3 2
www.pudim.com.br

Significa que o programa deverá baixar a pagina web "www.pudim.com.br" com nível de ignorancia igual a 3 e distancia das imagens igual a 2.
>CASO NENHUM ARGUMENTO SEJA FORNECIDO, o agente trabalhará com os parâmetros padrão: Nivel de ignorância = 1 e Distância das imagens = 2.
>AMBOS OS PARÂMETROS DEVEM SER FORNECIDOS JUNTOS ou seja, se quer especificar o nivel de ignorancia, deve também especificar a distancia das imagens. Ou especifica ambos, ou nenhum.

////EXECUÇÃO
---REQUISITOS
Para execução do programa, é necessário ter a JVM java oracle 16 definida como padrão e o programa wkhtmltopdf instalado.

---EXECUÇÃO
Basta ir ao diretório do programa pelo terminal e executar o comando: ./exe
>Com isso o programa irá ler o arquivo t.txt para input.
>As fases de processamento serão escritas no terminal.

---USANDO O AGENTE SEPARADAMENTE
É possível executar o agente em uma imagem já baixada.
->PARA ISSO DEVE-SE:
-Colocar a imagem no mesmo diretório do agente
-Nomear a imagem enumerada seguido pela extensão png. A contagem começa do zero, sendo assim as imagens devem ser nomeadas: 0.png, 1.png, 2.png ...
-Executar pelo terminal com o comando: java -jar Agente.jar INT , sendo que o argumento INT deve ser substituído pela quantidade de imagens que devem ser processadas. Por exemplo, para executar o agente em 5 imagens, deve-se chamar pelo terminal: java -jar Agente.jar 5,e para executa-lo em 1 imagem: java -jar Agente.jar 1
>Imagens incompletas (imagens que foram cortadas com a borda da pagina) serão ignoradas.
>Há duas imagens de teste na pasta "testes para agente", basta copiar as imagens para fora da pasta e executar pelo terminal com o comando: java -jar Agente.jar 2
>Não há limite para a quantidade de imagens que podem ser usadas como input, porém todas devem ser nomeadas de acordo, NÃO SE ESQUEÇA DE SEMPRE COMEÇAR COM 0, CASO NÃO TENHA UMA IMAGEM CHAMADA 0.png, CASO A QUANTIDADE DE IMAGENS SEJA MENOR DO QUE A PASSADA COMO ARGUMENTO, OU UMA DAS IMAGENS NÃO ESTEJA NOMEADA DE ACORDO, O PROGRAMA IRÁ ABORTAR.

////OUTPUT
Será criado um diretório chamado "resultado" dentro do mesmo diretório em que o programa foi executado.
>Dentro de tal diretório será criada uma pasta para cada pagina (link) dada como input, enumeradas a partir de 1.
>Dentro das pastas estarão as imagens reconhecidas, já cortadas.
>Caso chame o programa várias vezes, as imagens já baixadas NÃO serão sobrescritas. Será criada uma nova pasta, continuando com a enumeração.
>Todos os outputs serão em formato png.
>A resolução dos resultados será a mesma que tais imagens tinham no input.
