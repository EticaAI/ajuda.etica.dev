# ajuda.etica.dev
**[trabalho em progresso] Guia de ajuda do Águia Pescadora, a PaaS comunitária da Etica.AI**

_TL;DR: use a PaaS comunitária da [Etica.AI ↗](https://etica.ai/) baseada no
[Tsuru](#tsuru) para executar pontualmente tarefas pesadas ou manter online
suas aplicações que (idealmente, mas não obrigatoriamente) seguem a metodologia
de [aplicação de 12 fatores](#aplicação-de-12-fatores).
**Não atendemos usuários finais**, mas você, como administrador de time e
responsável, pode. Nós procuramos manter com servidores que rodam as
apps dos colegas com ótimo custo-benefício ao ponto de ter opção poder dar
processamento computacional de alta qualidade decente sem cobrar valor
financeiro de pessoas desenvolvedoras que ajudam comunidades de base (Veja
[Etica.AI Infrastructure: Clusters & VPS ↗](https://github.com/orgs/EticaAI/projects/2);
e caso encontre mais baratos, avise!)_.

<!--
_TL;DR: use o [Tsuru](#tsuru) para executar pontualmente ou manter online
permanentemente em [servidores ↗](https://github.com/orgs/EticaAI/projects/2) da
organização [Etica.AI ↗](https://etica.ai/) suas aplicações que (idealmente)
seguem a metodologia para software-como-serviço
[Aplicação de 12 fatores](#aplicação-de-12-fatores)._
-->

----

<!-- TOC depthFrom:2 -->

- [Tópicos de ajuda](#tópicos-de-ajuda)
    - [Aplicação de 12 fatores](#aplicação-de-12-fatores)
    - [Backup](#backup)
        - [Backup de informações de aplicações em Etica.Dev em datacenter remotos](#backup-de-informações-de-aplicações-em-eticadev-em-datacenter-remotos)
        - [Backup de informações em de servidores remotos em Etica.Dev](#backup-de-informações-em-de-servidores-remotos-em-eticadev)
        - [App Etica.Dev como agente de backups](#app-eticadev-como-agente-de-backups)
    - [Domínios](#domínios)
        - [HTTPS dos domínios](#https-dos-domínios)
    - [Tsuru](#tsuru)
    - [Minio](#minio)
- [Páginas espelho de ajuda.etica.dev](#páginas-espelho-de-ajudaeticadev)
- [Licença de softwares de pessoas desenvolvedoras que usam app.etica.dev](#licença-de-softwares-de-pessoas-desenvolvedoras-que-usam-appeticadev)
- [Licença da documentação ajuda.etica.dev](#licença-da-documentação-ajudaeticadev)

<!-- /TOC -->

----

## Tópicos de ajuda

### Aplicação de 12 fatores

O PaaS da Etica.AI funcionará melhor se sua solução respeitar o conceito de
_Aplicação de 12 fatores_ que pode ser lido em <https://12factor.net/pt_br/>
e cuja introdução é:

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
que sejam fotos de caezinhos 🐶! É uma forma de se acostumar com boas práticas
a serem seguitas em qualquer servidor que use.

#### App Etica.Dev como agente de backups
Você poderá usar um ou mais apps hospedados em Etica.Dev como um
[agente inteligente ↗](https://pt.wikipedia.org/wiki/Agente_inteligente) para
automatizar tarefas de backups em servidores remotos sem armazear dados na nossa
nuvem.

<!--
- https://github.com/sameersbn/docker-gitlab/pull/737
-->

### Domínios
Você pode usar um ou mais domínios de topo (sejam eles pagos
[ou gratúitos ↗](https://freenom.com)) — recomendado caso queira servir para
usuários finais! — bastando que use o tsuru client e no seu provedor de DNS
aponte os domínios para `CNAME app.etica.dev`. Por questão de comodidade (ou
por você explicitamente ter interesse) pode configurar seu app como subdomínio
de `*.app.etiva.dev`, que já foi preparado para apontar para o cluster de
servidores da Etica.Dev.

#### HTTPS dos domínios
Temos SSL automática com Let's Encrypt por padrão em qualquer domínio/subdomínio
apontado para nossos servidores.

Note que [você pode revotar nossa capacidade de servir conteudo HTTPS](https://letsencrypt.org/docs/revoking/)
sem ajuda de pessoa que tenha nível de acesso de administração da nuvem.

### Tsuru
> [Tsuru ↗](https://tsuru.io/) é um software de Plataforma Como Serviço ("PaaS")
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
Útil para clientes sem suporte a HTTPS ou o quando até mesmo aplicação que
fornece a documentação está em manutenção.

# Licença

## Licença de softwares de pessoas desenvolvedoras que usam app.etica.dev
**Exceto quando explicitado contrário e de forma clara, assuma que pessoas
autoras (assim como é tendência em legislações ao redor do mundo) mantém todos
os direitos de cópia e que licença do software é proprietaria.**

O uso do PaaS da Etica.AI e/ou reaproveitamento de código ou documentação nosso
por pessoas desenvolvedoras não implica em obrigação nem mesmo moral de dedicar
software a licenças que não exigem licenciamento reciproco como Domínio Publico
ou BSD. Pessoas autoras são livres até mesmo para relicenciar conteúdo dedicado
ao Domínio público em licenças proprietarias ou de reprocidade forte, como GPL.

<!--
- Permissive and Copyleft Are Not Antonyms https://opensource.org/node/875
-->

<!--
Por padrão autores mantém todos os direitos de cópia

Softwares das pessoas desenvolvedoras que usam app.etica.dev sem licença
explícita ou que possam ser facilmente inferidas de 
-->

## Licença da documentação ajuda.etica.dev

[![Domínio Público](img/dominio-publico.png)](UNLICENSE)

Na medida do possível segundo a lei, [EticaAI](https://github.com/EticaAI)
renunciou a todos os direitos autorais e direitos conexos ou vizinhos a este
trabalho para o [Domínio Público](UNLICENSE).

Citação de fonte original em obras derivadas em nome da
[Etica.AI](https://etica.ai) é bem vinda, mas não é exigida, nem mesmo como
obrigação moral.

Favor renomear referências a Etica.Dev (em especial os guias de como conectar
ao Tsuru) caso reuse para outros usuários.
