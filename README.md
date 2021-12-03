## Relatório Atividade 1 - Leonardo Batista Leite da Silva (1885189)

### Parte 1 - Prática


| ![image](https://user-images.githubusercontent.com/31395627/144533609-a71b924a-4914-4ac3-b129-28c8c3bbd977.png) |
|:--:| 
| *Imagem 1 - Trocas de mensagens entre os clientes sendo visualizado no software WireShark* |

A imagem 1 representa o software WireShark exibindo as troca de mensagem entre o Cliente 1 e o Cliente 2. 
Neste caso, ainda não existe nenhuma criptografia envolvida e conseguimos ler as mensagens no software.
O arquivo `Client.py` envia as mensagens usando o código:

    data = msg.encode()
    self.client(host, port, data)  
  
Para resolver este problema e criptografar as mensagens trocadas entre os cliente, foi adicionado no código
uma importação da biblioteca `cryptography` reponsável por criptografar as mensagens.

    from cryptography.fernet import Fernet

    #chave constante para codificar e descodificar as mensagens.
    key =  'nUxC7FgTgRGgOvSarbeXVg0aVxQw1RKZoKaNJDFRvbk='
    f = Fernet(key)
  
E quando for enviar as mensagens com a criptografia, utilizamos:

    data = f.encrypt(msg.encode())
    self.client(host, port, data)

Entretanto, é necessário haver uma descriptografia das mensagens, para isso:

    print(f.decrypt(data).decode() + '\n>>')

No código temos uma chave única para codifiar e descodificar as mensagens trocadas entre os clientes.
Após ao acrescimo da biblioteca, o software WireShark nao foi mais capaz de ler a mensagens trocadas.
A imagem abaixo mostra como é feito a leitura pelo software.
Porem, as mensagens entre os clientes é feito normalmente e os mesmos são capazes de se comunicar, mas não para quem não está inserido na conversa.



| ![image](https://user-images.githubusercontent.com/31395627/144628644-37e49ff3-464d-4cb8-8303-bba67bae02e5.png) |
|:--:| 
| *Imagem 2 - Mensagens entre os clientes criptografadas no software WireShark* |


### Parte 2 - Referências
- Documentação Fernet (symmetric encryption) disponível em: https://cryptography.io/en/latest/
