<p align="center">
  <img src="https://media.elektor.com/media/catalog/product/cache/9cc822bfc6a57f9729d464b8b5e0e0df/j/o/joy-it-nodemcu-esp32-development-board_front.png" width="300" /><br/>
Caixinha de Música - Projeto da Owlficinas de Microcontroladores <br/>
</p>

<br/>

## :pushpin: Descrição

Nosso projeto é uma caixinha de música em que um buzzer emite as notas musicais em forma de beep (leia-se "campainha") e uma bailarina gira a partir de um motor rotativo. O objetivo do projeto era trabalhar com música a partir de uma união entre o clássico da caixinha de música com o moderno das possibilidades que a tecnologia tem a oferecer. Assim, projetamos uma caixinha de som em que se escolhe a música a partir de um site no aparelho celular do usuário.


<br/>

## :robot: Montagem do dispositivo físico

### Lista de materiais

| Quantidade | Nome | Link para referência |
| --- | --- | --- |
| 1 | ESP32 e cabo USB | https://www.baudaeletronica.com.br/placa-doit-esp32-bluetooth-e-wifi.html |
| 4 | Buzzer Ativo Programável | https://www.eletrogate.com/buzzer-ativo-5v?utm_source=Site&utm_medium=GoogleMerchant&utm_campaign=GoogleMerchant&gad=1&gclid=Cj0KCQjwk96lBhDHARIsAEKO4xauBy1Zdvprys4j1ThOaqRjedv45X4-ec5x3n0ZeytOvHP0reTzkQkaAu_0EALw_wcB |
| 4 | Motor Rf Rotativo | https://produto.mercadolivre.com.br/MLB-3379691027-motor-rf-300-para-robotica-dvd-playstation-59v-6600rpm-_JM?matt_tool=63064967&matt_word=&matt_source=google&matt_campaign_id=14303413826&matt_ad_group_id=133431076203&matt_match_type=&matt_network=g&matt_device=c&matt_creative=584156655540&matt_keyword=&matt_ad_position=&matt_ad_type=pla&matt_merchant_id=5069482700&matt_product_id=MLB3379691027&matt_product_partition_id=310365260760&matt_target_id=pla-310365260760&gclid=Cj0KCQjwk96lBhDHARIsAEKO4 |
| X | Jumpers variados | --- |
| 1 | Protoboard | --- |
| 1 | Fonte de alimentação - PowerBank | https://www.americanas.com.br/produto/2706391331 |

### Lista de conexões

| Componente | Pino da placa |
| --- | --- |
| Buzzer | 13 |
| Motor | esp: VIN, protoboard 25 - |


### Funcionamento dos sensores e atuadores

#### Buzzer Ativo Programável:

O buzzer programável ("sem borrachinha") é um atuador analógico, uma vez que transforma energia elétrica em ação mecânica (no caso, energia acústica) não binária (podendo programar diferentes frequências para os beeps/sons emitidos pelo buzzer, ou seja, por isso analógico).
Especificações Técnicas: tensão de operação entre 3,5 e 5 volts de beep contínuo.


#### Motor Rf Rotativo:

O motor rotativo é um tipo de atuador eletromecânico que converte energia elétrica em movimento rotativo mecânico. No caso, é um atuador digital, pois funciona em valores binários, ou seja, ou ele está desligado ou ligado e rotacionando a uma velocidade específica.
Especificações Técnicas: Motor DC com tensão de operação a 5,9V RF(radio-frequência)-300CA.


### Circuito

<p align="center">
Figura - Diagrama do circuito<br/>
  <img src= "https://cdn.discordapp.com/attachments/1131229981071134811/1131409755127173160/IMG-20230719-WA0034.jpg" /><br/>
</p>
Esse é o esqueleto do nosso circuito. Os fios amarelo, verde e preto que conectam a placa do ESP32 à protoboard e conectam pinos na própria protoboard são jumpers os quais conduzem corrente elétrica pelo circuito. Já tanto o buzzer quanto o motor possuem um fio pra ser a "alimentação", conduzindo a energia elétrica até eles que, como atuadores, a transformarão em energia mecânica e um segundo fio a fim de continuar o caminho da corrente elétrica. Assim, fecha-se o circuito (e o caminho da corrente e da energia, consequentemente) e conclue-se o funcionamento do sistema.
<br/>

<br/>

## :electric_plug: Funcionamento do sistema

Videozinho do sistema funcionando:



https://github.com/RafaCaminag/CaixaDeMusica/assets/131477600/dfbc8468-6d95-4a33-b938-ffb1f3825fc7



informações:
- Requisitos do Código: nosso código se propõe a oferecer ao usuário a experiência de escolher uma música em um site em seu celular e, então, ouvi-la tal qual como em uma caixinha de música (pelo buzzer programado) com uma bailarina rodando (pelo motor rotativo). 
- Estrutura de Arquivos e Funcionamento do Código: Das linhas 1-6 do código, importamos arquivos e funções necessárias para o pleno funcionamento do código. De 8-98, definimos as notas musicais e suas freqências que serão usadas no buzzer programável. De 100-184, definimos as músicas (programando a sequência de notas) e criamos as funções necessárias para que as músicas possam ser reproduzidas. De 186-190, criamos a função para escolher e tocar a música escolhida. A 192, conecta o motor a um pino da protoboard e o "ativa". Da 194-416 e da 526-529, faz o ESP32 emitir sinal de rede para que possa ser conectado à rede e ao aparelho do usuário. Além disso, da 207-411, cria uma web page para a escolha da música pelo usuário. E, finalmente, da 417-524, conecta as partes anteriores do código, fazendo-as funcionar em conjunto.


<br/>

## :busts_in_silhouette: Contribuir no projeto

### Features implementadas

- Motor rotativo para fazer o movimento da bailarina da caixinha de música tradicional;
- Buzzer com beeps de diferentes frequências a fim de programar e reproduzir músicas;
- Conectar o ESP32 a uma rede e criar um site para que o usuário que se conecte possa escolher a música (dentre as opções disponíveis) de maneira onlinne por meio de um dispositivo próprio.


### Features para incrementar no projeto

- Implementar uma telinha OLed a fim de fazer o nome da música escolhida ser exibida na tela;
- Implementar um motor de velocidade de rotação programável;
- Colocar de fato uma boneca para ser a bailarina da caixinha de música;
- Realmente colocar o sistema dentro de uma caixinha.


