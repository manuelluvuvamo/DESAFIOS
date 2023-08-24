# Desafio programação ✨

Por favor leiam este documento do começo ao fim, com muita atenção.
O intuito deste teste é avaliar seus conhecimentos técnicos em programação.
O teste consiste em parsear [este arquivo de texto(CNAB)](https://github.com/manuelluvuvamo/CNAB/blob/main/CNAB.txt) e salvar suas informações(transações financeiras) em uma base de dados a seu critério.
Este desafio deve ser feito por você em sua casa. Gaste o tempo que você quiser, porém normalmente você não deve precisar de mais do que algumas horas.

# Instruções de entrega do desafio

1. Primeiro, faça um fork deste projeto para sua conta no Github (crie uma se você não possuir).
2. Em seguida, implemente o projeto tal qual descrito abaixo, em seu clone local.
3. Por fim, envie via email o projeto ou o fork/link do projeto para seu contato.

# Descrição do projeto

Você recebeu um arquivo CNAB com os dados das movimentações finanaceira de várias lojas.
Precisamos criar uma maneira para que estes dados sejam importados para um banco de dados.

Sua tarefa é criar uma interface web que aceite upload do [arquivo CNAB](https://github.com/manuelluvuvamo/CNAB/blob/main/CNAB.txt), normalize os dados e armazene-os em um banco de dados relacional e exiba essas informações em tela.

**Sua aplicação web DEVE:**

1. Ter uma tela (via um formulário) para fazer o upload do arquivo
2. Interpretar ("parsear") o arquivo recebido, normalizar os dados, e salvar corretamente a informação em um banco de dados relacional, **se atente as documentações** que estão logo abaixo.
3. Exibir uma lista das operações importadas por lojas, e nesta lista deve conter um totalizador do saldo em conta
4. Ser escrita na sua linguagem de programação de preferência
5. Ser simples de configurar e rodar, funcionando em ambiente compatível com Unix (Linux ou Mac OS X). Ela deve utilizar apenas linguagens e bibliotecas livres ou gratuitas.
6. Git com commits atomicos e bem descritos
7. PostgreSQL ou MySQL
8. Readme file descrevendo bem o projeto e seu setup
9. Incluir informação descrevendo como consumir o endpoint da API

**Sua aplicação web não precisa:**

1. Lidar com autenticação ou autorização (pontos extras se ela fizer, mais pontos extras se a autenticação for feita via OAuth).
2. Ser escrita usando algum framework específico (mas não há nada errado em usá-los também, use o que achar melhor).
3. Documentação da api.(Será um diferencial e pontos extras se fizer)

# Documentação do CNAB - copia.xlsx
    
   **Deve conter os cabeçalhos na primeira fila como exemplificado à seguir**

| tipo | data | valor | bi | cartao | hora | dono_loja | nome_loja
| --- | ---  | ---  | ---  | ---  | ---  | ---  | --- 
| 1 | 2021-12-24 | 10000 | 000000000LA010 | 12345678901234 | 11:21:00 | Dono da loja | Kayla System Solutions

# Documentação sobre os tipos das transações

| Tipo | Descrição | Natureza | Sinal |
| ---- | -------- | --------- | ----- |
| 1 | Débito | Entrada | + |
| 2 | Boleto | Saída | - |
| 3 | Financiamento | Saída | - |
| 4 | Crédito | Entrada | + |
| 5 | Recebimento Empréstimo | Entrada | + |
| 6 | Vendas | Entrada | + |
| 7 | Recebimento TED | Entrada | + |
| 8 | Recebimento DOC | Entrada | + |
| 9 | Aluguel | Saída | - |


 # Documentação do CNAB.csv e CNAB.txt
   **Não deve conter os cabeçalhos na primeira fila como exemplificado à seguir**
    
    
    3;2019-03-01;0000014200;096206760LA017;475300003153;15:34:53;JOÃO MACEDO;BAR DO JOÃO       
    5;2019-03-01;0000013200;556418151UE063;312300007687;14:56:07;MARIA JOSEFINA;LOJA DO Ó - MATRIZ
    3;2019-03-01;0000012200;845152543BE073;677700001313;17:27:12;MARCOS PEREIRA ;MERCADO DA AVENIDA
    2;2019-03-01;0000011200;096206760LA017;364800000099;23:42:34;JOÃO MACEDO ;BAR DO JOÃO       
    1;2019-03-01;0000015200;096206760LA017;123400007890;23:30:00;JOÃO MACEDO;BAR DO JOÃO       
    2;2019-03-01;0000010700;845152543BE073;872300009987;12:33:33;MARCOS PEREIRA;MERCADO DA AVENIDA
    2;2019-03-01;0000050200;845152543BE073;847300001231;23:12:33;MARCOS PEREIRA;MERCADO DA AVENIDA
    3;2019-03-01;0000060200;232702987ZR056;677700001313;17:27:12;JOSÉ COSTA;MERCEARIA 3 IRMÃOS
    1;2019-03-01;0000020000;556418151UE063;123400003324;090002;MARIA JOSEFINA;LOJA DO Ó - MATRIZ
    5;2019-03-01;0000080200;845152543BE073;312300007687;145607;MARCOS PEREIRA;MERCADO DA AVENIDA
    2;2019-03-01;0000010200;232702987ZR056;847300001231;23:12:33;JOSÉ COSTA;MERCEARIA 3 IRMÃOS
    3;2019-03-01;0000610200;232702987ZR056;677700001313;17:27:12;JOSÉ COSTA;MERCEARIA 3 IRMÃOS
    4;2019-03-01;0000015232;556418151UE063;123400006678;10:00:00;MARIA JOSEFINA;LOJA DO Ó - FILIAL
    8;2019-03-01;0000010203;845152543BE073;234400001222;12:32:22;MARCOS PEREIRA;MERCADO DA AVENIDA
    3;2019-03-01;0000010300;232702987ZR056;677700001313;17:27:12;JOSÉ COSTA;MERCEARIA 3 IRMÃOS
    9;2019-03-01;0000010200;556418151UE063;622800009090;00:00:00;MARIA JOSEFINA;LOJA DO Ó - MATRIZ
    4;2019-03-01;0000050617;845152543BE073;123400002231;10:00:00;MARCOS PEREIRA;MERCADO DA AVENIDA
    2;2019-03-01;0000010900;232702987ZR056;872300009987;12:33:33;JOSÉ COSTA;MERCEARIA 3 IRMÃOS
    8;2019-03-01;0000000200;845152543BE073;234400001222;12:32:22;MARCOS PEREIRA;MERCADO DA AVENIDA
    2;2019-03-01;0000000500;232702987ZR056;767700008778;14:18:08;JOSÉ COSTA;MERCEARIA 3 IRMÃOS
    3;2019-03-01;0000019200;845152543BE073;677700001313;17:27:12;MARCOS PEREIRA;MERCADO DA AVENIDA
# Avaliação

Seu projeto será avaliado de acordo com os seguintes critérios.

1. Sua aplicação preenche os requerimentos básicos?
2. Você documentou a maneira de configurar o ambiente e rodar sua aplicação?
3. Você seguiu as instruções de envio do desafio?

Adicionalmente, tentaremos verificar a sua familiarização com as bibliotecas padrões (standard libs), bem como sua experiência com programação orientada a objetos a partir da estrutura de seu projeto.

# Referência

Este desafio foi baseado neste outro desafio: ByCodersTec/desafio-dev

---

Boa sorte!
