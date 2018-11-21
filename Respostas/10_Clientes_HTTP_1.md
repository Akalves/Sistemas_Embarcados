1. Especifique algumas portas importantes pré-definidas para o protocolo TCP/IP.

  Tanto no protocolo TCP como no UDP, é comum o uso das portas de 1 a 1024, já que a aplicação destas é padronizada pela IANA 
(Internet Assigned Numbers Authority). De acordo com essa entidade, eis algumas das portas TCP mais utilizadas:

* 21 - FTP;
* 23 - Telnet;
* 25 - SMTP;
* 80 - HTTP;
* 110 - POP3;
* 143 - IMAP;
* 443 - HTTPS.

2. Com relação a endereços IP, responda:

(a) Qual é a diferença entre endereços IP externos e locais?

* IP Local: é utilizado para identificar um dispositivo em uma rede interna, também chamada de Intranet.
* IP Externo: é utilizado para identificar um dispositivo conectado à Internet. É um endereço único (não 
possui nenhum outro dispositivo com o mesmo IP) porém dinâmico, o que significa que o endereço pode ser 
alterado.

(b) Como endereços IP externos são definidos? Quem os define?

Este endereço é atribuído a um host na rede externa pelo proprietário do host. O endereço é atribuído
globalmente de um endereço roteável ou de um espaço de rede.

(c) Como endereços IP locais são definidos? Quem os define?

Este endereço é configurado como um parâmetro do sistema operacional do computador ou recebido através dos
protocolos da alocação de endereço dinâmico tais como o DHCP. 

(d) O que é o DNS? Para que ele serve?

O DNS - Domain Name System (Sistema de Nomes de Domínios), funciona como um sistema de tradução de 
endereços IP para nomes de domínios.

3. Com relação à pilha de protocolos TCP/IP, responda:

(a) O que são suas camadas? Para que servem?

O conjunto de protocolos pode ser visto como um modelo de camadas (Modelo OSI), onde 
cada camada é responsável por um grupo de tarefas, fornecendo um conjunto de serviços 
bem definidos para o protocolo da camada superior. As camadas mais altas, estão 
logicamente mais perto do usuário (chamada camada de aplicação) e lidam com dados mais 
abstratos, confiando em protocolos de camadas mais baixas para tarefas de menor nível 
de abstração.

(b) Quais são as camadas existentes? Para que servem?

1 - Rede (Interface com Rede)
(1ª e 2ª camada OSI): Essa é a parte conhecida como física pois trata-se das tecnologias usadas para 
as conexões como: Ethernet, Wi-Fi, Modem, etc. No modelo OSI, essa camada também 
é física, porém, é dividido em duas partes: física e enlace de dados. A física é 
a parte do hardware e a enlace de dados é a parte lógica do hardware; mac address.

2 - Internet
(3ª camada OSI): Para TCP/IP o protocolo é IP, MPLS
Essa parte é responsável pelas conexões entre as redes locais, estabelecendo assim 
a interconexão. 

3 - Transporte
(4ª camada OSI): TCP, UDP, SCTP
Essa parte controla a comunicação host-a-host.

4 - Aplicação
(5ª, 6ª e 7ª camada OSI): HTTP, HTTPS, FTP, DNS
Essa parte contém todos os protocolos para um serviço específico de comunicação de 
dados em um nível de processo-a-processo (por exemplo: como um web browser deve se 
comunicar com um servidor da web). 

(c) Quais camadas são utilizadas pela biblioteca de sockets?

(d) As portas usadas por servidores na função bind() se referem a qual camada?

Une um nome ao seu socket. De modo bem prático, essa função serve para associar uma porta em sua
máquina local para o seu socket. Essa função é muito usada com outra função, a listen().
A função bind() é muito usada em servidores, socket servidor.

(e) Os endereços usados por clientes na função connect() se referem a qual camada?

Essa é a conhecida função responsavel pela conexão telnet. Essa função é responsável pela
conexão de seu socket cliente, com um servidor qualquer.

4. Qual é a diferença entre os métodos GET e POST no protocolo HTTP?

Os principais métodos de comunicação HTTP são: GET e POST.

Visibilidade – A grande diferença entre os métodos GET e POST provavelmente é a 
visibilidade. Uma requisição GET é enviada como string anexada a URL, enquanto 
que a requisição POST é encapsulada junto ao corpo da requisição HTTP e não pode 
ser vista.

Tamanho – Como a requisição GET é feita via URL, obviamente há uma limitação no tamanho 
da mensagem enviada. A string não pode conter mais que 255 caracteres(embora exista 
diferenças entre navegadores, mas em geral o limite é 255). Já na requisição POST não 
há limitações de comprimento da mensagem, já que a mesma é enviada no corpo da requisição 
HTTP.

Performance – A requisição GET é relativamente mais rápida, já que ela é mais simples. 
Na requisição POST há uma perda de tempo no encapsulamento da mensagem.

Tipos – Já que GET é enviado via URL, então nós sabemos que ela só transporta textos. 
A requisição POST não tem restrições, pode transportar tanto texto, como dados binários.

Favoritos/Bookmarks – Por se tratar apenas de uma URL, a requisição GET pode ser armazenada 
em cache, ou em um sistema de bookmark(favoritos). A mesma coisa não é possível para 
requisições POST.

Método HTML Padrão – GET é o método HTML padrão. Para submeter um formulário HTML usando 
POST é preciso especificar no atributo “method” o valor “POST”.

Dados – As requisições GET são limitadas ao padrão ASCII, enquanto que requisições POST 
também podem usar o atributo “enctype” com o valor “multipart/form-data”, que faz uso do 
padrão UCS(Universal Multiple-Octet Coded Character Set).
