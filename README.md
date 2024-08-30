# Configura-o-Rede-Simples



# Utilizei o Laboratorio da Redes Brasil no EVE NG



# Os dispositivos configurados são da MikroTik


![image](https://github.com/user-attachments/assets/260dc6e7-4e47-4915-8f06-db65b5f26316)


→ Vamos fazer a configuração dessa seguinte rede.

→ Vamos dividir a rede 1 em duas Lans e na rede 2 fazendo apenas uma Lan.

→ Vamos fazer com que ambas se comuniquem e troquem informações entre si e consigam ter acesso a internet

- Vamos começar acessando o roteador 1 (R1)
- Vamos no canto esquerdo do EVE, clicamos em lab details e copiamos o link do roteador 1

![image](https://github.com/user-attachments/assets/e9428526-41a2-44ce-95b3-a27b3fd61843)


- Dentro do Winbox, colocamos o link do R1 que copiamos
- No campo de login usamos o usuário admin e deixamos sem senha

![image](https://github.com/user-attachments/assets/1a6cabeb-5d64-40ae-913e-a0e6f5cf1add)


- Depois que fizermos o nosso primeiro acesso, colocamos uma senha no nosso roteador

![image](https://github.com/user-attachments/assets/fce646d4-0932-4622-a7c6-33a62daa10ac)


- Vamos mudar o nosso do nosso Roteador
- Vamos em System e depois em Identity

![image](https://github.com/user-attachments/assets/67ecaf25-051e-4cc0-a081-ba5058c0e2de)


![image](https://github.com/user-attachments/assets/1903ea95-8c05-41f9-a604-6529034e1327)


- Vai abrir essa caixinha e colocamos o nome do nosso roteador e aplicamos

- Depois disso vamos renomear as interfaces do nosso roteador
- Então, clicamos no menu de interfaces

![image](https://github.com/user-attachments/assets/ce6b841b-a443-4b7c-85a2-64d84a5797f9)


- Se as interfaces aparecerem nessa ordem, conseguimos alterar para que apareça na ordem de 1a 5
- Para fazermos isso, abrimos o nosso terminal e digitamos o seguinte comando: interface/ethernet/reset [f]

![image](https://github.com/user-attachments/assets/341446fe-85f9-4d38-9474-a7916b4c12a2)


![image](https://github.com/user-attachments/assets/0285b973-828a-431a-9cd9-6aa289d75802)


![image](https://github.com/user-attachments/assets/3465e807-aa49-4a9e-9163-0b6f7b6e4f21)


- Agora vamos renomear as interfaces de acordo com a nossa topologia criada no Eve (Clicamos na nossa interface e colocamos para onde essa interface vai, onde está conectada)

![image](https://github.com/user-attachments/assets/2489ae2b-172a-4b06-a1a8-9ac126e36f00)

- Agora, vamos ativar o nosso link de internet utilizando o DHCP Client
- Então vamos em IP, DHCP Client
- Damos um duplo clique na interface que já vai estar criada, selecionamos a interface que recebemos o nosso link de internet e deixamos as opções marcadas

![image](https://github.com/user-attachments/assets/eda200ae-cb76-4e46-bd04-fd640d3d8740)


![image](https://github.com/user-attachments/assets/a418fe35-b376-4030-b430-bae91b058f45)


- Como queremos ter duas Lan’s dentro da nossa rede vamos configurar um IP e um Servidor DHCP para nossos dois PCs
- Vamos em IP, Address, Clicamos no + e vamos adicionar nossa primeira faixa de número IP colocando como nossa interface o nosso VPC-01: 192.168.0.1/24

![image](https://github.com/user-attachments/assets/2a6bdf3f-86fb-48d0-b4ef-341c5c62f4b1)


![image](https://github.com/user-attachments/assets/9cec1fc6-0b67-42d1-87e5-edf3cb450225)


- Agora vamos adicionar o nosso DHCP-Server nessa mesma interface que colocamos o endereço de IP
- Então vamos em IP, DHCP-Server e em DCHCP-Setup e apenas apertamos next (Ele já define tudo com base no IP que colocamos)

![image](https://github.com/user-attachments/assets/de7163cc-6520-4042-b060-d40ace5c02fd)


![image](https://github.com/user-attachments/assets/dca1e191-c879-4d87-9d3e-7d8b0ad632bd)


- Fazemos a mesma coisa agora para o nosso segundo VPC, utilizando o IP: 192.168.50.0/24

- Depois que fizemos isso, os dois PCs já receberam um endereço de IP e já conseguem se comunicar entre si, então agora vamos fazer com que ambos consigam ter acesso a internet
- Então vamos em IP, Firewall e clicamos em NAT

![image](https://github.com/user-attachments/assets/d0d5c064-b6a3-41aa-aaba-96ddc03716af)


![image](https://github.com/user-attachments/assets/7f19b522-f3f0-4736-92de-d49b03173609)


- Vamos fazer uma regra simples de NAT apenas para termos acesso a internet
- Vamos utilizar o Mascarado/masquerade: Para quando formos mandar alguma informação para internet, ele vai trocar o IP da nossa maquina e colocar o endereço de IP da nossa conexão que vai para internet
- Então clicamos no + para adicionarmos uma regra de NAT

![image](https://github.com/user-attachments/assets/76e2641d-60c9-495b-9585-4d5df97af523)


- No Chain deixamos como srcnat
- Depois clicamos em action e selecionamos a opção masquerade
- E no Out.Interface selecionamos a nossa interface de saída para internet que no caso é a interface que recebemos o link

![image](https://github.com/user-attachments/assets/2ffdd4f6-178c-4865-a49b-1c5ac3cec010)


- Se acessarmos o VPC-01 e tentarmos acessar pingar com o VPC-02 e acessar a internet, dará certo
- Pingando do VPC-01 para o google

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/e582be75-2600-402c-80a0-b5387f0ac888/image.png)

- Pingando do VPC-01 para o VPC-02

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/50dfeb54-b2d5-4774-8707-a854f118ec96/image.png)

- Agora vamos acessar o nosso R2 (Da mesma maneira que foi feito o acesso passado)
- Colocamos uma senha, mudamos o nome e renomeamos as interfaces

- Como queremos deixar tudo na mesma LAN, vamos criar uma bridge e vamos adicionar as interfaces que estão o VPC-01 e VPC-02
- Então vamos clicar em Bridge, clicamos no + e criamos uma Bridge

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/e59546f0-3005-4b9e-9951-5c64802b48a7/image.png)

- Depois vamos em ports e adicionamos as nossas duas portas que estão conectadas os nossos VPCs

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/ea10c245-df29-4d1e-a944-abb3b2df1cd5/image.png)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/5c3448ad-1226-4479-9b8a-c690084affc0/image.png)

- Agora vamos adicionar um endereço de IP para nossa bridge
- Então clicamos em IP, Address e adicionamos o IP: 192.168.100.0/24

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/2a0dfe41-5ea3-489b-ad1d-54ad043be319/image.png)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/e0160728-0415-43a6-b2ed-b51e317145d8/image.png)

- Agora vamos adicionar um servidor de DHCP nessa Bridge
- Então vamos em IP, DHCP Server, DHCP Setup, selecionamos a interface da nossa bridge e clicamos em next

- Com isso a comunicação da nossa segunda Lan está feita
- Então, se tentarmos pingar do VPC-01 para o VPC-02 dessa Lan, teremos resposta
- Pingando do VPC-01 para o VPC-02

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/f4e17ad7-94e7-4b7f-8690-818a4978e202/image.png)

- Mas, se tentarmos pingar de um VPC da primeira Lan para um VPC da segunda LAN, não teremos rota

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/7582f484-d4e3-4217-a299-598bff7bed48/image.png)

- Para fazermos que esses PCs se comuniquem entre si, estabelecemos uma faixa de IP para essa ponte: IP: 10.0.0.0/24
- Então vamos adicionar essa faixa de IP no nosso roteador 1
- Então vamos em IP, Address e adicionamos essa faixa de IP e na interface selecionamos o nosso R1

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/240ec60e-b027-40d6-966f-34cea8429f67/image.png)

- E vamos fazer a mesma coisa no nosso R2

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/466156e5-6aeb-4103-b36e-59d4a3009c09/image.png)

- Agora vamos traçar a rota do nosso R1 para o nosso R2
- Então vamos em IP, Routes, Clicamos no + e vamos adicionar uma nova rota

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/9aafba6d-c6ca-41ee-b6cd-2eb951eda2d7/image.png)

- Então, no Dst.Address (Endereço de Destino), colocamos o endereço de IP da bridge que colocamos no nosso R2 e no Gateway colocamos o endereço de IP que colocamos para ligarmos os dois roteadores (Endereço de IP da ponte do R2)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/c2517070-c9d2-49e3-93f4-2ec47c4b5005/image.png)

- E no nosso R2, como temos duas Lans diferentes no nosso R1, vamos ter que fazer uma rota para cada umas das Lans
- No Dst.Addres colocamos o endereço de IP da primeira Lan e no Gateway o endereço da ponte que colocamos para o nosso R1

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/1a40be86-0b2b-437e-9d87-39a439e3f64a/image.png)

- Colocando o IP da segunda Lan

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/6d8dc721-a0c6-4e9b-b427-7985f3312ea3/image.png)

- E com isso agora os computadores das duas redes conseguem se comunicar
- Pingando do VPC-01 (Rede 1) para o VPC-01 (Rede 2)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/c9e5d431-34ab-4722-9677-db0c06926194/image.png)

- Mas mesmo assim os computadores da Rede 2 ainda não possuem acesso a internet

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/27649791-7bd5-4703-a89c-11f7ad1c673d/image.png)

- Se formos ver as rotas do segundo roteador, vemos que ele não possui a rota padrão para internet: 0.0.0.0/24
- Então vamos adicionar uma rota padrão para o segundo roteador
- E no gateway colocamos o IP da ponte que definimos para o R1 (Que é o roteador que possui a regra de firewall e também recebe o link de internet)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/057a51be-57bb-4375-a2e8-ffd71347dfe3/image.png)

- Testando pingar do VPC-02 para internet

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/e4e648b0-f9d5-48de-8456-c992377e42ea/image.png)
