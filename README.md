Os Equalisadores de onda, consistem em controlar as frequências de um determinado sinal a fim de modificar a amplitude de uma certa frequência.

No caso de equalisadores de audio mais convencionais, utilizamos uma divisão simplificada das freqências, sendo elas denominadas baixas, médias e altas frequências, que regulam o grave (bass), medio(middle) e agudo(treble) respectivamente.

Para fim deste projeto, podemos considerar a seguinte sequência de blocos:



Agora a pergunta seria: Qual tipo de filtro devemos utilizar?

Para responder esta pergunta, vamos olhar a tabela de filtros a segui, olhando qual filtro possui a característica que queremos, que é um filtro que possua uma linearidade maior em uma certa faixa de frequências.

Ao observarmos, o filtro que melhor se adapta é o Butterworth, que possui uma qualidade 0.707 e proporciona uma amplitude homogênia.



Agora que já sabemos qual o melhor tipo, precisamos avaliar qual deverá ser a ordem deste filtro pois será ela que determinará o quão precido o filtro será, ou seja, após a frequência de corte, ele diminuirá n*20 dB por década. Para isso iremos utilizar a Equação 1, onde n é a ordem do filtro.

A partir da equação e das informações supracitadas, chegamos em um filtro Butterworth de segunda ordem, que nos proporcionará um ganho uniforme no passa faixa, além de uma queda relativamente brusca (40 dB por década) nas frequências de corte.l





Para determinarmos as frequências de corte, efetuamos pesquisas em livros, sites da internet e catálogos de equipamentos, onde verificamos que as frequências de corte são 300Hz e 3KHz.

A partir destes valores, e da equação padrão para determinação de frequências de corte, e fixando o valor da capacitância em 10uF, que proporciona uma constante de tempo baixa, chegamos nos valores de 53k e 5.3k para as frequências 300Hz e 3Khz respectivamente.

É importante notar que todo filtro Butterworth efetua uma defasagem de fase da ordem 90º, e que, no caso do Passabanda , que é formado por uma sequência de dois filtros, ocorre uma defasagem de 180º e que precisamos defasar este de -90º. Para isso adicionamos um "defasador" antes do passabanda.

A partir dos dados que possuímos, projetamos, simulamos, montamos e testamos os filtros necessários, utilizando a seguinte lista de componentes:

Protoboard
Ampop (TL074)
Capacitores de 10 uF
Resistores de 53K, 5.3K e 6.8K
Potenciômetros de 100K










Ao efetuarmos testes, notamos uma relação Sinal Ruido muito baixa, visto que estávamos efetuando uma amplificação no final de cada filtro.

Para uma segunda versão do atual projeto, iremos efetuar as seguintes tarefas.

 

Avaliar técnicas de redução de ruídos
Projetar divisor de tensão para utilizar somente uma fonte DC
Estudar controle remoto do dispositivo
Finalizar projeto PCB.
 

Bibliografia

 

- Integrated Electronics by Millman & Halkias

McGraw-Hill.

- Microelectronic Circuits 6th edition

 

Download da apresentação 1





Na segunda versão do Equalizador de 3 bandas, modificamos o projeto para obtermos uma redução de de ruídos, além de implementarmos ele em PCB, tornando o projeto mais robusto e mais organizado.

A fim de reduzirmos o ruído existente, decidimos por atuar no limite de saturação dos ampops, ou seja, adicionamos um amplificador de aproximadamente 8x na entrada do circuito.

 



Com esta modificação, foi necessário alterar também o modo com que os ampops de saída de cada faixa de equalização atuam, fazendo com que estes atuassem como atenuadores de sinal e não como amplificadores, como ocorrido na 1ª versão do projeto.

 



Após esta modificação do projeto, teremos o circuito a seguir, o qual deverá ser transferido para uma PCB.

 



Para montarmos o projeto na PCB, utilizamos o software EAGLE - freeware e importando algumas bibliotecas externas do Monowave.

Após montarmos o circuito e posicionarmos as peças na placa, obtivemos o seguinte esquemático.

 



Podemos notar que para fazermos tal placa, precisaríamos de impressão duplaface, além de trilhas de 10mm, o que dificulta a impressão e a montagem (sendo impossível fazer na DTL do SG11). Para isso, pegamos os padrões de impressão, assim como quais arquivos deveriam ser gerados para a confecção ser feita na Divisão Técnico Laboratorial do SG11 da Universidade de Brasília.

No final deste post tem um tutorial feito pelo Pedro Salum para auxiliar a impressão na DTL.

Ao observarmos o padrão necessário, tivemos que efetuar uma divisão do projeto da PCB em 3 partes, passa baixa, passa faixa e passa alta e depois interconectá-las por meio de fios.





Próximos passos

 - Empilhar placas a fim de reduzir espaço

 - criar uma case para o dispositivo

 - embutir um divisor de tensão a fim de utilizar uma fonte portátil.

 

Download da Apresentação (em breve)

Baixar Tutorial Eagle para Geber (em breve)
