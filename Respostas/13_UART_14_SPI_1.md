1. Cite as vantagens e desvantagens das comunicação serial:

(a) Assíncrona (UART).

A comunicação assíncrona não faz uso do sinal de clock, o que reduz a quantidade de fios necessária para 
sua utilização. Porém o envio de dados é complicado e possui maior taxa de erro. 
No caso da comunicação UART, a transmissão é full-duplex, o que significa que o dispositivo pode enviar 
e receber dados ao mesmo tempo. A ligaçãop é feita por dois pinos Rx/Tx que dependem do boud rate como 
referência. O baud rate especifica a velocidade da transmissão de dados. Para que os dois dispositivos se 
comuniquem é necessário que os dois possuam a mesma taxa de transmissão.

(b) SPI.

A comunicação SPI também é full-duplex, possui boa velocidade de comunicação e não tem limites para número
de escravos.

* Funcionamento:

Mestre--> Seleciona o escravo que vai se comunicar pelo pelo pino SS. 
Envio de dados --> Os dados são enviados pelo mestre através do pino MOSI.
Escravo --> Envia uma resposta, se necessário, pelo pino MISO.

* Ligação:

- Paralela: utiliza um pino MOSI, MISO e clock para todos os dispositivos e um pino SS para cada escravo 
ligado a comunicação.

- Cascata: utiliza um pino SS para todos os dispositivos ligados na comunicação, o que reduz a velocidade 
de comunicação.

2. Considere o caso em que a Raspberry Pi deve receber leituras analógico/digitais de um MSP430, e que a 
comunicação entre os dois é UART. É tecnicamente possível que o MSP430 mande os resultados da conversão
A/D a qualquer hora, ou ele deve aguardar a Raspberry Pi fazer um pedido ao MSP430? Por quê?

É possivél porque a comunicação UART é full-duplex e não utiliza a configuração mestre-escravo, que é 
responsável pelo envio de requisição de dados.

3. Considere o caso em que a Raspberry Pi deve receber leituras analógico/digitais de um MSP430, que a 
comunicação entre os dois seja SPI, e que o MSP430 seja o escravo. É tecnicamente possível que o MSP430 
mande os resultados da conversão A/D a qualquer hora, ou ele deve aguardar a Raspberry Pi fazer um pedido 
ao MSP430? Por quê?

Não é possível. o MSP430 configurado como escravo deve aguardar a requisição da Rapberry (mestre) para só 
então fazer o envio dos dados.

4. Se o Raspberry Pi tiver de se comunicar com dois dispositivos via UART, como executar a comunicação 
com o segundo dispositivo?

Seria necessário o uso do bit AD para informar o endereço dos dispositivos resultando na seguinte
sequência:
Endereço do dispositivo 1 --> Mensagem --> Endereço do dispositivo 2 --> Mensagem

5. Se o Raspberry Pi tiver de se comunicar com dois dispositivos via SPI, como executar a comunicação
com o segundo dispositivo?

Na comunicação SPI, para que o mestre se comunique com mais de um dispositivo existe um quarto fio que 
envia o endereço do escravo. Todos os dispositivos se conectam ao fio de endereço e apenas recebe a
mensagem o dispositivo referente ao endereço da linha.
