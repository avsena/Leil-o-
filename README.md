 Componentes:
•	João Victor Silva Soares de Oliveira
•	Agripino Lincoln Sousa Fonseca
•	Jeandson Cabral Silva
•	Lucas Ruan Andrade Almeida
•	Alfredo Victor do Nascimento Souza Sena


Descrição do aplicativo:
O aplicativo foi desenvolvido utilizando o conceito de threads. O servidor executa um thread para escutar as mensagens que chegam. Assim que o cliente se conecta ele envia uma mensagem para o servidor especificando o tipo do cliente e o id do cliente. Ao receber a mensagem o servidor cria uma segunda thread em paralelo que fica escutando somente as mensagens deste cliente, isso é feito para cada cliente conectado.
Para estabelecer uma conexão entre cliente e servidor foi desenvolvido um cenário dentro do aplicativo Virtual Box. 

Cenário:
3 maquinas virtuais interligadas através da rede interna do Virtual Box, para realizar a configuração basta colocar a placa de rede, nas configurações da máquina virtual, em modo bridge. Uma para o servidor, outra para o cliente vendedor e outra para o cliente comprador.

Recursos de cada máquina:
•	Sistema Operacional: Windows 10 64bits – versão Home;
•	Memória RAM: 2gb (2048mb);
•	Armazenamento: HD - 15gb;

Os endereços estão estáticos, então cada máquina deverá ter os seguintes IP’s:
•	Servidor: 192.168.1.1;
•	Cliente Vendedor: 192.168.1.2;
•	Cliente Comprador: 192.168.1.3
Gateway: 192.168.1.0

Todo o a aplicação foi desenvolvida utilizando a linguagem python, então todas as maquinas virtuais devem estar com o framework python instalado em sua versão mais recente, que até então é 3.10.4 e para Windows 64bits. Link abaixo:
https://www.python.org/downloads/windows/

Recomendação: faça o download e instalação do framework python antes de colocar as placas de rede no modo bridge, pois as maquinas virtuais perderão a conectividade com a internet. Durante a instalação do framework marque a opção “Add Python to PATH”, assim será possível executar comandos através do prompt de comando.

Execução:
Para executar a aplicação do leilão é necessário criar um arquivo dentro de uma pasta na área de trabalho com o nome da aplicação e extensão “py” e colar todo o código dentro deste arquivo, um para cada componente. Para o servidor crie, dentro da pasta, um arquivo chamado “servidor.py”, para o cliente vendedor “clientevendedor.py” e para o cliente comprador “clientecomprador.py”.
Depois de criar os arquivos é necessário abrir o prompt de comando dentro dessa passa. É possível abrir segurando shift + botão direito e clicando na opção “Abrir janela do prompt de comando aqui”, ou simplesmente abrir o prompt e acessar a pasta por linha de código. Em seguida execute o comando:
->	python + nome do arquivo
->	ex: python servidor.py

Servidor: Ao executar o servidor ele fica escutando todas as mensagens que chegam e quando chegam ele trata e responde de acordo com o tipo do cliente conectado e o tipo da mensagem.
Cliente comprador: Ao se conectar ele lista todos os artigos. É possível escolher duas opções “Atualizar lista”, onde ele envia uma mensagem para o servidor e recebe todos os artigos cadastrados até o momento. A segunda opção é “Dar lance”, onde o cliente especifica o id do produto, o valor do lance e o e-mail. 
Cliente vendedor: Ao se conectar envia para o servidor o nome do artigo, a descrição e o valor mínimo do lance. É responsável por encerrar o leilão digitando a palavra “exit” e teclando enter, assim recebe as informações do vencedor.
