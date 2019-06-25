# ajuda.etica.dev
**[trabalho em progresso] Guia de ajuda do Águia Pescadora, o PaaS comunitário da Etica.AI**

----

<!-- TOC depthFrom:2 -->

- [Tópicos de ajuda](#tópicos-de-ajuda)
    - [Aplicação de 12 fatores](#aplicação-de-12-fatores)
    - [Backup](#backup)
        - [Backup de informações de aplicações em Etica.Dev em datacenter remotos](#backup-de-informações-de-aplicações-em-eticadev-em-datacenter-remotos)
        - [Backup de informações em de servidores remotos em Etica.Dev](#backup-de-informações-em-de-servidores-remotos-em-eticadev)
        - [App EticaDev como agente de backups](#app-eticadev-como-agente-de-backups)
    - [Domínios](#domínios)
    - [Tsuru](#tsuru)
    - [Minio](#minio)
- [Páginas espelho de ajuda.etica.dev](#páginas-espelho-de-ajudaeticadev)
- [Licença de softwares de pessoas desenvolvedoras que usam app.etica.dev](#licença-de-softwares-de-pessoas-desenvolvedoras-que-usam-appeticadev)
- [Licença da documentação ajuda.etica.dev](#licença-da-documentação-ajudaeticadev)

<!-- /TOC -->

----

## Tópicos de ajuda

### Aplicação de 12 fatores

O PaaS da Etica.AI funcionará melhor se sua aplicação respeitar o conceito de
_Aplicação de 12 fatores_ que pode ser lido em <https://12factor.net/pt_br/> e
tem a introdução resumida a seguir.

> Na era moderna, software é comumente entregue como um serviço: denominados *web apps*, ou *software-como-serviço*. A aplicação doze-fatores é uma metodologia para construir softwares-como-serviço que:
>
> * Usam formatos **declarativos** para automatizar a configuração inicial, minimizar tempo e custo para novos desenvolvedores participarem do projeto;
> * Tem um **contrato claro** com o sistema operacional que o suporta, oferecendo **portabilidade máxima** entre ambientes que o executem;
> * São adequados para **implantação** em modernas **plataformas em nuvem**, evitando a necessidade por servidores e administração do sistema;
> * **Minimizam a divergência** entre desenvolvimento e produção, permitindo a **implantação contínua** para máxima agilidade;
> * E podem **escalar** sem significativas mudanças em ferramentas, arquiteturas, ou práticas de desenvolvimento.
>
> A metodologia doze-fatores pode ser aplicada a aplicações escritas em qualquer linguagem de programação, e que utilizem qualquer combinação de serviços de suportes (banco de dados, filas, cache de memória, etc).
>
> — Criado por Adam Wiggins / Liberado sob licença MIT : opensource.org/licenses/MIT

### Backup

#### Backup de informações de aplicações em Etica.Dev em datacenter remotos
Recomendamos que para informações que não possam ser recriadas a qualquer
momento de bases de dados versionadas em Git ou
[imagens Docker publicas](https://hub.docker.com/) você, pessoa desenvolvedora,
ou pessoa que administra seu time, crie uma automação usando apps extras de
[Tsuru](#tsuru) e as envie para servidores remotos. Sua aplicação, sua
responsabilidade.

#### Backup de informações em de servidores remotos em Etica.Dev
Sim, você pode usar o PaaS da Etica.AI como **opção extra** para receber
Backups de outros projetos, porém recomendamos faça backups encriptados, mesmo
que sejam fotos de caezinhos 🐶.

#### App EticaDev como agente de backups
Você poderá usar um ou mais apps hospedados em Etica.Dev como um
[agente inteligente](https://pt.wikipedia.org/wiki/Agente_inteligente) para
automatizar tarefas de backups em servidores remotos sem armazear dados na nossa
nuvem.

<!--
- https://github.com/sameersbn/docker-gitlab/pull/737
-->

### Domínios
Você pode usar seu próprio domínio de topo (seja ele pago
[ou gratúito](https://freenom.com)) — recomendado caso queira servir para
usuários finais! — apotando no provedor de DNS `CNAME app.etica.dev`.
Adicionalmente por usar subdomínio de `*.app.etiva.dev` que já esta apontado
para cluster de servidores da Etica.Dev.

Temos SSL automática com Let's Encrypt por padrão em qualquer domínio/subdomínio
apontado para nossos servidores. E sim, [você pode revotar nossa capacidade
de gerar HTTPS](https://letsencrypt.org/docs/revoking/) sem ajuda da
administração da nuvem.

### Tsuru
> [Tsuru](https://tsuru.io/) é um software de Plataforma Como Serviço ("PaaS")
extensível e de verdadeiramente de código aberto (sem nem mesmo versão
comercial) e que é pronto para uso em produção com Docker desde 2013.

- [Tsuru](tsuru-paas/)
  - [Administração de Nuvem](tsuru-paas/administracao-da-nuvem/)
  - [Administração de Time](tsuru-paas/administracao-de-time/)
  - [Desenvolvimento](tsuru-paas/desenvolvimento/)
    - [Olá Mundo com Tsuru PaaS na Etica.Dev](tsuru-paas/ola-mundo/)

### Minio
> [Minio](https://min.io) é Armazenamento de Objetos Compatíveis com Amazon S3
que é 100% código aberto e padrão corporativo.

Neste momento não temos uma implementação de Minio padrão no Etica.Dev. Você
pode implementar o seu usando [Tsuru](#tsuru).

## Páginas espelho de ajuda.etica.dev
É possíve acessar esta documentação também via <http://ajuda-dev.etica.ai/>.
Útil para clientes sem suporte a HTTPS ou o caso onde a documentação está
em manutenção.

# Licença

<!--
## Licença de softwares de pessoas desenvolvedoras que usam app.etica.dev

Softwares das pessoas desenvolvedoras que usam app.etica.dev sem licença
explícita ou que possam ser facilmente inferidas de 
-->

## Licença da documentação ajuda.etica.dev

Domínio Público.

Favor renomear referências a Etica.Dev (em especial os guias de como conectar
ao Tsuru) caso reuse para outros usuários.
