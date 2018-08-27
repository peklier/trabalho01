               
# TRABALHO 01:  Semaforup
Trabalho desenvolvido durante a disciplina de Banco de Dados do Integrado

# Sumário

### 1. COMPONENTES<br>
Integrantes do grupo<br>
Christian Lopes de Souza:christianlopessouza@gmail.com<br>
Gabriel de Souza Klier Conceição:desouzagabriel80@gmail.com<br>
...

### 2.INTRODUÇÃO E MOTIVAÇAO<br>
<br>e motivação da escolha realizada. <br>

> As formas de tirar uma carteira de habilitação nos dias atuais ficaram facilitadas, logo prevendo que a idade mínima é de 18 anos, logo a quantidade de pessoas que possuem veículos acabam por aumentar e assim tende a continuar.
Com a facilidade de comprar um veículo, usado ou novo, seja por meio de longos financiamentos ou não. Existem por volta de 42 milhões de Carteiras de Motoristas ativas no Brasil.
Com o forte avanço e o crescente número de veículos, as ruas devem estar devidademente preparadas para se adaptar a um grande volume de tráfego que varia diariamente dependendo do momento. Para isto, a forma de semáforos com tempo fixo já não vai ser a melhor proposta para conter o atraso no transito em função da demanda. Sendo assim, nosso trabalho visa o desenvolvimento de um semáforo inteligente e totalmente autônomo que conduza o tráfego de uma forma que atenda a demanda de veículos locais.
Em um cruzamento de duas ou mais vias existem movimentos que não podem ser feitos simultaneamente, pois podem se colidir, estabelencendo normas de controle de direito de passagem com o objetivo de melhorar o fluxo do tráfego e reduzir os riscos de acidentes.
 
 

### 3.MINI-MUNDO<br>

Entrevista com o usuário e identificação dos requisitos.<br>
Descrição textual das regras de negócio definidas como um  subconjunto do mundo real 
cujos elementos são propriedades que desejamos incluir, processar, armazenar, 
gerenciar, atualizar, e que descrevem a proposta/solução a ser desenvolvida.

> O sistema que foi proposto para o Semaforup, trata-se de um sistema simples que calcula proporcionalmente de 1 para 1 os semáforos cadastrados na base de dados. Os semáforos com essa tecnologia e esse software são chamados de "Semafobots", eles tem uma programação e a utilização de sensores que permitem calcular o tempo que outro semáforo vinculado irá ficar aberto. A informção é captada por um sensor que se localiza no chão paralelo ao semáforo, então, as informações relacionadas a quantidade de carros (fluxo) e velocidade média por minuto. 
>Com essas informações dentro da memória, todos os semáforos que tenham alguma relação ou vinculo, que esteja relacionada à algum cruzamento ou ruas que dependem do fluxo da outra. Logo é feita uma escala de 1 a 100 (percentual) em coparação de dois semafobots e fará um percentual do tempo limite que foi imposto à um semáforo - que é de 60 segundos - e dividirá proporcinalmente equivalente a média do fluxo de carros (por minuto) para cada uma dessas ruas. Em um exemplo para ficar mais claro .: Uma rua chama "AA" e outra rua chamada "BB", dentro de um minuto passaram 54 carros na Rua AA e 33 carros na Rua BB, sendo assim com essas informações, o software soma os valores das quantidade de carros (33+54=87) e dividem cada valor da Rua pelo todo (33/87=~38%), (54/87=~62%).  Agora tendo uma relação de 38(Rua AA) para 62(Rua BB), temos que 38% de 1 minuto ficará destinado para o semáforo referente a Rua AA e 62% destinado a Rua BB, sendo assim 22.8 e  37,2 segundos. 
>Há em caso de cruzamentos, relações específicas que fazem média com várias ruas, tendo uma base de dados maior para armazenar mais informações, um sistema híbrido para evitar acidente e diminuir a demora do transito. Haverá o semáfaro com uma configuração fixa, que será avaliada se será necessário a utilização desse recurso. A "configuaração fixa" é de um tempo fixo, determinada por ruas específicas ou ruas de modo geral, que por padrão são 30 segundos, mas podem ser alteradas ou cadastradas com tempo diferente.


### 4.RASCUNHOS BÁSICOS DA INTERFACE (MOCKUPS)<br>
Neste ponto a codificação não e necessária, somente as ideias de telas devem ser desenvolvidas. O princípio aqui é pensar na criação da interface para identificar possíveis informações a serem armazenadas e/ou descartadas <br>

Sugestão: https://balsamiq.com/products/mockups/<br>

![Alt text](https://github.com/semaforup/trabalho01/blob/master/imagens/img.png?raw=true "Famoso Mockup do Balq")
![Arquivo PDF do Protótipo Balsamiq feito para Empresa Devcom](https://github.com/semaforup/trabalho01/blob/master/arquivos/NewProject.pdf "Semaforup")


#### 4.1 TABELA DE DADOS DO SISTEMA:
![Tabela](https://github.com/semaforup/trabalho01/blob/master/arquivos/TabelaSemaforup%20(1).xlsx "Modelo Conceitual")

    a) Esta tabela deve conter todos os atributos do sistema e um mínimo de 10 linhas/registros de dados.
    b) Esta tabela tem a intenção de simular um relatório com todos os dados que serão armazenados 
    e deve ser criada antes do modelo conceitual
    c) Após criada esta tabela não deve ser modificada, pois será comparada com os resultados finais na conclusão do trabalho
    
    
#### 4.2 QUAIS PERGUNTAS PODEM SER RESPONDIDAS COM O SISTEMA PROPOSTO?
    a) Como não haverá conflitos de semáforos abertos ao mesmo tempo na mesma tragetória?
    b) Como as informações serão armazenadas para se adaptarem ao fluxo?
    c) Como os operários do sistema de liberdade para alterarem quais funções?
    d) Como serão obtidas as informações necessárias para que os semáforos funcionem de forma inteligente? 
    e) Como é determinado qual via o semáforo deve permanecer mais tempo aberto? 

    
>## Marco de Entrega 01 em: (24/03/2018)<br>

### 5.MODELO CONCEITUAL<br>    
![Modelo Conceitual](https://github.com/semaforup/trabalho01/blob/master/imagens/Conceitual_3.png "Modelo Conceitual")

   
## Marco de Entrega 01 em: (20/04/2018)<br>
#### 5.2 DECISÕES DE PROJETO
    
    EXEMPLO:
    a) Campo endereço: em nosso projeto optamos por um campo multivalorado e composto, pois a empresa 
    pode possuir para cada departamento mais de uma localização... 
    b) justifique!


#### 5.3 DESCRIÇÃO DOS DADOS 
    CPF: campo que armazena o número de Cadastro de Pessoa Física para cada cliente da empresa.<br>
    numero_semaforo: Campo que armazena o código de identificação do semáforo
    rua_semaforo: Campo que armazena o nome da rua em que o semáforo foi localizado
    bairro_semaforo: Campo que armazena o nome do bairro em que o semáforo foi localizado
    cidade_semaforo: Campo que armazena o nome da cidade em que o semáforo foi localizado
    cod_rua: Campo que armazena o código de identificação referente a rua em que o semáforo foi localizado
    cod_bairro: Campo que armazena o código de identificação referente a rua em que o semáforo foi localizado
    cod_cidade: Campo que armazena o código de identificação referente ao bairro em que o semáforo foi localizado
    cod_geral: Campo que armazena o código dos três códigos (cod_cidade,cod_bairro,cod_rua) em um só
    cod_sensor: Campo que armazena o código dos sensores relacionados ao semáforo
    quant_semaforo_vinc: Campo que armazena a quantidade de semáforos que estão vinculado a um determinado semáforo
    quant_carros_rua_min: Campo que a armazena a quantidade de carros que passam em uma rua por minuto
    quant_carros_rua_hr_med: Campo que a armazena a média de carros que passam em uma rua por hora   
    med_quant_carros_dia: Campo que a armazena a média de carros que passam em uma rua por dia 
    minuto: Campo que armazena o minuto em que o sensor faz o cálculo e a analise da rua
    hora: Campo que armazena a hora em que o sensor faz o cálculo e a analise da rua
    velocid_med_rua: Campo que a armazena a velocidade dos carros que passam na rua por minuto
    tempo_fechado: Campo que armazena o tempo, baseado nos cálculos , que o semáforo ficará fechado
    nome_usuario_comum: Campo que armazena o nome de usuário dos usuários comuns, ou seja, que não tem controle sobre nenum dos semáforos
    senha_usuario_comum: Campo que armazena o nome dos usuários comuns
    nome_operario: Campo que armazena o nome de usuário dos operários, esses que tinham controle sobre os semáforos
    senha_operario: Campo que armazena a senha dos operários 
    data_analise: Campo que armazena a data em que foi feita analise por minuto
    cod_usuario: Campo que armazena o código de identificação dos usuarios comuns
    cod_operario: Campo que armazena o código de identificação dos operários


    
    
>## Marco de Entrega 01 em: (12/05/2018)<br>
### 6	MODELO LÓGICO<br>
(https://github.com/semaforup/trabalho01/blob/master/imagens/mapa_logico_mdbd.png?raw=true "Modelo Lógico")

### 7	MODELO FÍSICO<br>
(https://github.com/semaforup/trabalho01/blob/master/arquivos/3 "Modelo Físico")          
        
### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
#### 8.1 DETALHAMENTO DAS INFORMAÇÕES
(https://github.com/semaforup/trabalho01/blob/master/arquivos/inserts.txt "Inserimento de Informações")       

#### 8.2 INCLUSÃO DO SCRIPT PARA CRIAÇÃO DE TABELA E INSERÇÃO DOS DADOS
(https://github.com/semaforup/trabalho01/blob/master/arquivos/2 "Insert+Modfis")

#### 8.3 INCLUSÃO DO SCRIPT PARA EXCLUSÃO DE TABELAS EXISTENTES, CRIAÇÃO DE TABELA NOVAS E INSERÇÃO DOS DADOS
(https://github.com/semaforup/trabalho01/blob/master/arquivos/1 "Insert,Modelo Fisico,Drop")


### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
    OBS: Incluir para cada tópico as instruções SQL + imagens (print da tela) mostrando os resultados.<br>
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>
#### 9.2	CONSULTAS DAS TABELAS COM FILTROS WHERE (Mínimo 4)<br>
    select * from usuário where cod_usuario = 123
    https://github.com/semaforup/trabalho01/blob/master/imagens/print%20where/where2.png
    
    select * from usuário where nome_usuario = 'Geovani';
    
    https://github.com/semaforup/trabalho01/blob/master/imagens/print%20where/where3.png
    select * from usuário where nome_usuario = 'Marcos';
    
    https://github.com/semaforup/trabalho01/blob/master/imagens/print%20where/where4.png
    select * from rua where cod_rua = 454;
#### 9.3	CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E TABELAS OU CAMPOS RENOMEADOS (Mínimo 11)
    select * from usuário where rua_semaforo > 500 and rua_semaforo < 800;
    https://github.com/semaforup/trabalho01/blob/master/imagens/print%20where/isnot1.png
    
    select * from rua where cod_rua > 200 and cod_rua<700
    https://github.com/semaforup/trabalho01/blob/master/imagens/print%20where/isnot2.png
    
    select * from rua where cod_rua > 400 and cod_rua<900
    https://github.com/semaforup/trabalho01/blob/master/imagens/print%20where/isnot3.png
    
    select * from cidade where cod_cidade = 22 or cod_cidade=47
    https://github.com/semaforup/trabalho01/blob/master/imagens/print%20where/isnot4.png
    
    select nome_cidade from cidade where cod_cidade > 40
    https://github.com/semaforup/trabalho01/blob/master/imagens/print%20where/isnot5.png
    
    select * from usuário where rua_semaforo > 500 and rua_semaforo < 800;
    https://github.com/semaforup/trabalho01/blob/master/imagens/print%20where/isnot1.png
    
    select * from semaforo where tempo_fechado < 20
    https://github.com/semaforup/trabalho01/blob/master/imagens/print%20where/as3.png
    
    select * from semaforo where tempo_fechado < 30
    https://github.com/semaforup/trabalho01/blob/master/imagens/print%20where/as3.png
    
    select * from bairro as bar where nome_bairro = 'Serra Leoa'
    https://github.com/semaforup/trabalho01/blob/master/imagens/print%20where/as1.png
    
    select * from cidade as city where cod_cidade > 40
    https://github.com/semaforup/trabalho01/blob/master/imagens/print%20where/as2.png
    
    select * from semaforo as sinal where tempo_fechado < 20
    https://github.com/semaforup/trabalho01/blob/master/imagens/print%20where/as3.png
    
#### 9.4	CONSULTAS QUE USAM OPERADORES LIKE E DATAS (Mínimo 12) <br>
    a) Criar outras 5 consultas que envolvam like ou ilike
    b) Criar uma consulta para cada tipo de função data apresentada.


    
#### 9.5	ATUALIZAÇÃO E EXCLUSÃO DE DADOS (Mínimo 6)<br>
    DROP TABLE bairro ;
    DROP TABLE semáforo ;
    DROP TABLE cidade ;
    ALTER TABLE cidade DROP cod_cidade;
    update bairro set cod_bairro =88 where cod_bairro = 14;  
    update bairro DROP nome_bairro;  
 

## Marco de Entrega 02 em: (16/06/2018)<br>
### ATUALIZAÇÃO DA DOCUMENTAÇÃO DOS SLIDES PARA APRESENTAÇAO SEMESTRAL (Mínimo 6 e Máximo 10)<br>
<br>
    Data de Entrega: (30/06/2018)
<br>

#### 9.7	CONSULTAS COM GROUP BY E FUNÇÕES DE AGRUPAMENTO (Mínimo 6)<br>

#### 9.8	CONSULTAS COM LEFT E RIGHT JOIN (Mínimo 4)<br>
#### 9.9	CONSULTAS COM SELF JOIN E VIEW (Mínimo 6)<br>
        a) Uma junção que envolva Self Join
        b) Outras junções com views que o grupo considere como sendo de relevante importância para o trabalho
#### 9.10	SUBCONSULTAS (Mínimo 3)<br>

#### 9.11	LISTA DE CODIGOS DAS FUNÇÕES E TRIGGERS<br>
        Detalhamento sobre funcionalidade de cada código.
        a) Objetivo
        b) Código do objeto (função/trigger)
        c) exemplo de dados para aplicação
        d) resultados em forma de tabela/imagem
<br>


#### 9.12	GERACAO DE DADOS (MÍNIMO DE 100 MIL REGISTROS PARA PRINCIPAL RELAÇAO)<br>
        a) principal tabela do sistema deve ter no mínimo 100 mil registros
        b) tabelas diretamente relacionadas a tabela principal 10 mil registros
        c) tabelas auxiliares de relacao multivalorada mínimo de 10 registros
        d) registrar o tempo de inserção em cada uma das tabelas do banco de dados
        e) especificar a quantidade de registros inseridos em cada tabela
        Para melhor compreensão verifiquem o exemplo na base de testes:<br>
        https://github.com/discipbd2/base-de-testes-locadora
        

#### 9.13	Backup do Banco de Dados<br>
        Detalhamento do backup.
        a) Tempo
        b) Tamanho
        c) Teste de restauração (backup)
        d) Tempo para restauração
        e) Teste de restauração (script sql)
        f) Tempo para restauração (script sql)
<br>

Data de Entrega: (Data a ser definida)
<br>

#### 9.14	APLICAÇAO DE ÍNDICES E TESTES DE PERFORMANCE<br>
    a) Lista de índices, tipos de índices com explicação de porque foram implementados nas consultas 
    b) Performance esperada VS Resultados obtidos
    c) Tabela de resultados comparando velocidades antes e depois da aplicação dos índices (constando velocidade esperada com planejamento, sem indice e com índice Vs velocidade de execucao real com índice e sem índice).
    d) Escolher as consultas mais complexas para serem analisadas (consultas com menos de 2 joins não serão aceitas)
    e) As imagens do Explain devem ser inclusas no trabalho, bem como explicações sobre os resultados obtidos.
    f) Inclusão de tabela mostrando as 10 execuções, excluindo-se o maior e menor tempos para cada consulta e 
    obtendo-se a media dos outros valores como resultado médio final.
<br>
    Data de Entrega: (Data a ser definida)
<br>   

### 10	ATUALIZAÇÃO DA DOCUMENTAÇÃO DOS SLIDES PARA APRESENTAÇAO FINAL (Mínimo 6 e Máximo 10)<br>
<br>
    Data de Entrega: (Data a ser definida)
<br>

### 11 Backup completo do banco de dados postgres 
    a) deve ser realizado no formato "backup" 
        (Em Dump Options #1 Habilitar opções Don't Save Owner e Privilege)
    b) antes de postar o arquivo no git o mesmo deve ser testado/restaurado por outro grupo de alunos/dupla
    c) informar aqui o grupo de alunos/dupla que realizou o teste.

    
### 12	TUTORIAL COMPLETO DE PASSOS PARA RESTAURACAO DO BANCO E EXECUCAO DE PROCEDIMENTOS ENVOLVIDOS NO TRABALHO PARA OBTENÇÃO DOS RESULTADOS<br>
        a) Outros grupos deverão ser capazes de restaurar o banco 
        b) executar todas as consultas presentes no trabalho
        c) executar códigos que tenham sido construídos para o trabalho 
        d) realizar qualquer procedimento executado pelo grupo que desenvolveu o trabalho

### 13	DIFICULDADES ENCONTRADAS PELO GRUPO<br>  

    
>## Marco de Entrega 04/Entrega Final em: (Data definida no cronograma)<br>

       
### 14  FORMATACAO NO GIT: https://help.github.com/articles/basic-writing-and-formatting-syntax/
<comentario no git>
    
##### About Formatting
    https://help.github.com/articles/about-writing-and-formatting-on-github/
    
##### Basic Formatting in Git
    
    https://help.github.com/articles/basic-writing-and-formatting-syntax/#referencing-issues-and-pull-requests
   
    
##### Working with advanced formatting
    https://help.github.com/articles/working-with-advanced-formatting/

#### Mastering Markdown
    https://guides.github.com/features/mastering-markdown/

### OBSERVAÇÕES IMPORTANTES

#### Todos os arquivos que fazem parte do projeto (Imagens, pdfs, arquivos fonte, etc..), devem estar presentes no GIT. Os arquivos do projeto vigente não devem ser armazenados em quaisquer outras plataformas.
1. Caso existam arquivos com conteúdos sigilosos, comunicar o professor que definirá em conjunto com o grupo a melhor forma de armazenamento do arquivo.

#### Todos os grupos deverão fazer Fork deste repositório e dar permissões administrativas ao usuário deste GIT, para acompanhamento do trabalho.

#### Os usuários criado GIT devem possuir o nome de identificação do aluno (não serão aceitos nomes como Eu123, meuprojeto, pro456, etc). Em caso de dúvida comunicar o professor.


Link para BrModelo:<br>
http://sis4.com/brModelo/brModelo/download.html
<br>


Link para curso de GIT<br>
![https://www.youtube.com/curso_git](https://www.youtube.com/playlist?list=PLo7sFyCeiGUdIyEmHdfbuD2eR4XPDqnN2?r
