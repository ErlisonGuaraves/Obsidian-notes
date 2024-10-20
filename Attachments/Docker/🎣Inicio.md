
Os sistemas, atualmente, têm diversas aplicações e ferramentas que interagem entre si para compor seu todo.

É mais ou menos esse caso que vamos visualizar e entender por que os *<mark style="background: #FFF3A3A6;">containers</mark>* podem ser úteis nessas situações. Porém, antes disso, vamos partir do básico da ideia de como chegamos a essa solução.
## Exemplo de <mark style="background: #FF5582A6;">problema</mark>:

Temos uma aplicação ***<mark style="background: #BBFABBA6;">Nginx</mark>*** que vai servir como um *<mark style="background: #BBFABBA6;">load balancer</mark>* (balanceador de carga) do nosso sistema. Além disso, temos uma aplicação ***<mark style="background: #FF5582A6;">Java</mark>*** e uma aplicação **<mark style="background: #D2B3FFA6;">C#</mark>** rodando com o *<mark style="background: #ADCCFFA6;">.NET</mark>*.

![Untitled](Attachments/Docker/Inicio/Untitled.png)

## Quais problemas podem ocorrer nessa situação?

Se observarmos cada uma dessas aplicações e ferramentas, podemos acabar tendo um **conflito de portas**, porque as 3 aplicações nesse cenário dependem da porta 80 para executar o fluxo necessário.

Além disso, como podemos **alterar as versões de maneira prática**? Se simplesmente fizéssemos o *downgrade* ou o *upgrade* da versão do C#, atualizando o .NET, quebraríamos algo? Precisamos desinstalar para instalar uma nova? O mesmo se aplica ao Java e ao Nginx: conseguiríamos atualizar de maneira prática?

Outra questão é a seguinte: como vamos ter um **controle de recursos de memória e de CPU** para essas aplicações? Por exemplo: a aplicação C# precisa de 100 *millicores* de CPU e 200 *megabytes* de memória para funcionar. Como podemos definir isso de maneira fácil?

![Untitled](Untitled%201.png)

## <mark style="background: #BBFABBA6;">Solução</mark> “<mark style="background: #FF5582A6;">Ruim</mark>”:

Existe uma solução já bem difundida, que não é recente e ajuda a resolver esses problemas: as **máquinas virtuais(VM).**

![Untitled](Untitled%202.png)

- **Hardware Definido**: O computador físico em si.
- **Sistema Operacional (SO)**: Pode ser Windows, Linux, Mac, etc.
- **Hypervisor**: Um software especial que permite criar e gerenciar máquinas virtuais.

graças ao **Hypervisor é possível instalar programas e dependências de maneira isolada, sem interferir com o sistema principal.**

Essa solução resolve esses problemas iniciais, mas a pergunta que fica nesse momento é a seguinte: **é realmente necessário fazer isso**?

Exemplo de arquitetura em VM’s:

![Untitled](Untitled%203.png)

Manter máquinas virtuais pode ser custoso tanto em termos de recursos de hardware quanto de administração. Vamos simplificar novamente considerando os custos:

1. **Custo de Hardware**: VMs consomem muitos recursos do computador, como CPU, memória e armazenamento. Isso significa que você precisa de um hardware potente e, muitas vezes, caro.
2. **Custo de Manutenção**: Gerenciar várias VMs requer mais tempo e esforço. Você precisa se preocupar com atualizações, segurança, backups, etc.

## Arquitetura em Container

arquitetura de um container é mais clean pois n utiliza de hypervisor além de n consumir tanto recurso quanto uma VM

![Untitled](Untitled%204.png)


```ad-question
title: Por que os *containers* são mais **leves** em relação a uma máquina virtual?
collapse: closed

dentro de um sistema operacional, temos vários containers, isto é, diversas aplicações sendo executadas. No entanto, eles funcionarão diretamente como **processos** dentro do nosso sistema.
```

```ad-question
title: Como eles garantem o **isolamento**?
collapse: closed

para garantir o isolamento entre cada um deles e o sistema operacional original, existe um conceito chamado ***namespaces***, que garantirá que cada um desses containers tenha capacidade de se isolar em determinados **níveis:**

- **PID: Provê isolamento dos processos rodando dentro do container**
- **NET: Provê isolamento de interfaces de rede**
- IPC: Provê isolamento da comunicação entre processos e memoria compartilhada
- MNT: Provê isolamento do sistema de arquivos/pontos de montagem
- UTS: Provê isolamento do kernel. Age como se o container fosse outro host

```

 ```ad-question
title: Como funcionam sem instalar um **sistema operacional**?
collapse: closed
graças ao *namespace* UTS, se executarmos nossos containers em uma máquina com kernel *Linux*, cada um dos containers, a princípio, também terá um pedaço desse kernel, mas devidamente isolado.

![Untitled](Untitled%205.png)

```

[instalação](instalação.md)

[🐟 Docker Hub](🐟%20Docker%20Hub.md)
