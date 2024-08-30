# Configura-o-Rede-Simples



# Utilizei o Laboratorio da Redes Brasil no EVE NG



# Os dispositivos configurados são da MikroTik


![image](https://github.com/user-attachments/assets/260dc6e7-4e47-4915-8f06-db65b5f26316)


→ Vamos fazer a configuração dessa seguinte rede.

→ Vamos dividir a rede 1 em duas Lans e na rede 2 fazendo apenas uma Lan.

→ Vamos fazer com que ambas se comuniquem e troquem informações entre si e consigam ter acesso a internet

- Vamos começar acessando o roteador 1 (R1)
- Vamos no canto esquerdo do EVE, clicamos em lab details e copiamos o link do roteador 1

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/ea43845f-2076-4824-9fd6-436e9512eec8/image.png)

- Dentro do Winbox, colocamos o link do R1 que copiamos
- No campo de login usamos o usuário admin e deixamos sem senha

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/cfe79e7d-0242-4bc4-874a-06980e19526d/image.png)

- Depois que fizermos o nosso primeiro acesso, colocamos uma senha no nosso roteador

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/a8f239ad-079d-46a7-ae6d-5da741654ef3/image.png)

- Vamos mudar o nosso do nosso Roteador
- Vamos em System e depois em Identity

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/285c6b2d-b73a-4e0a-b6f6-0c10074c32eb/image.png)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/1dddb124-f8e8-4166-aa03-d31f25e61d56/image.png)

- Vai abrir essa caixinha e colocamos o nome do nosso roteador e aplicamos

- Depois disso vamos renomear as interfaces do nosso roteador
- Então, clicamos no menu de interfaces

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/7beae94f-cabc-41c6-8b04-e6b4400947e2/image.png)

- Se as interfaces aparecerem nessa ordem, conseguimos alterar para que apareça na ordem de 1a 5
- Para fazermos isso, abrimos o nosso terminal e digitamos o seguinte comando: interface/ethernet/reset [f]

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/e8b2167e-e298-4a58-b0f5-6e6e72aa7311/image.png)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/97fd76a6-93c8-450c-ad78-cda2cecf415b/image.png)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/4e3f525c-42ba-4b6c-97f5-b40004cb101f/image.png)

- Agora vamos renomear as interfaces de acordo com a nossa topologia criada no Eve (Clicamos na nossa interface e colocamos para onde essa interface vai, onde está conectada)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/522fe014-3629-4d48-a117-b0e0474c2aae/image.png)

- Agora, vamos ativar o nosso link de internet utilizando o DHCP Client
- Então vamos em IP, DHCP Client
- Damos um duplo clique na interface que já vai estar criada, selecionamos a interface que recebemos o nosso link de internet e deixamos as opções marcadas

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/93c9e609-832c-4611-8ca9-1a58d5026d3d/image.png)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/2305a03b-3d29-459b-8d0b-58a7cdd25279/image.png)

- Como queremos ter duas Lan’s dentro da nossa rede vamos configurar um IP e um Servidor DHCP para nossos dois PCs
- Vamos em IP, Address, Clicamos no + e vamos adicionar nossa primeira faixa de número IP colocando como nossa interface o nosso VPC-01: 192.168.0.1/24

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/58b90622-4c17-460e-aa0e-97f3a2589672/image.png)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/9e935449-a26a-4cec-b651-b28db07b12f0/image.png)

- Agora vamos adicionar o nosso DHCP-Server nessa mesma interface que colocamos o endereço de IP
- Então vamos em IP, DHCP-Server e em DCHCP-Setup e apenas apertamos next (Ele já define tudo com base no IP que colocamos)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/7403b0c7-cdcb-4e8d-b693-2c8cc33793b5/image.png)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/1413e79e-3c7f-453d-85d7-2cb7d08c28ad/image.png)

- Fazemos a mesma coisa agora para o nosso segundo VPC, utilizando o IP: 192.168.50.0/24

- Depois que fizemos isso, os dois PCs já receberam um endereço de IP e já conseguem se comunicar entre si, então agora vamos fazer com que ambos consigam ter acesso a internet
- Então vamos em IP, Firewall e clicamos em NAT

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/b1be7fa5-00c5-4d89-81cb-ab0754fef68b/image.png)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/3a205c03-496f-4372-a26e-74bd4ff18a5f/image.png)

- Vamos fazer uma regra simples de NAT apenas para termos acesso a internet
- Vamos utilizar o Mascarado/masquerade: Para quando formos mandar alguma informação para internet, ele vai trocar o IP da nossa maquina e colocar o endereço de IP da nossa conexão que vai para internet
- Então clicamos no + para adicionarmos uma regra de NAT

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/a22dc5e6-6ea0-4101-baba-8f97dc689e94/image.png)

- No Chain deixamos como srcnat
- Depois clicamos em action e selecionamos a opção masquerade
- E no Out.Interface selecionamos a nossa interface de saída para internet que no caso é a interface que recebemos o link

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb9d4e53-4c27-4fa3-9ac9-43d152624db5/dedbae1c-750f-4ad5-8af7-7a80daa87526/image.png)

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
