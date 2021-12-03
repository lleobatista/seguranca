## Relatório Atividade 1 - Leonardo Batista Leite da Silva (1885189)

![image](https://user-images.githubusercontent.com/31395627/144533609-a71b924a-4914-4ac3-b129-28c8c3bbd977.png)

A imagem acima representa o software WireShark exibindo as troca de mensagem entre o Cliente 1 e o Cliente 2. 
Neste caso, ainda não existe nenhuma criptografia envolvida e conseguimos ler as mensagens no software.
Para resolver este problema e criptografar as mensagens trocadas entre os cliente, foi adicionado no código do arquivo `Client.py`
uma importação da biblioteca `cryptography` reponsável por criptografar as mensagens.

No código temos uma chave única para codifiar e descodificar as mensagens trocadas entre os clientes.
Após ao acrescimo da biblioteca, o software WireShark nao foi mais capaz de ler a mensagens trocadas.
A imagem abaixo mostra como é feito a leitura pelo software.
Porem, as mensagens entre os clientes é feito normalmente e os mesmos são capaz de ler entre eles, mas não para quem não está inserido na conversa.

![image](https://user-images.githubusercontent.com/31395627/144628644-37e49ff3-464d-4cb8-8303-bba67bae02e5.png)
