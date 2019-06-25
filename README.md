# ajuda.etica.dev
**[trabalho em progresso] Guia de ajuda do Águia Pescadora, o PaaS comunitário da Etica.AI**

## Tópicos de ajuda

### Backup
Não temos uma estratégia de backup automatizada neste momento. Você pode fazer
sua própria até mesmo usando o [Tsuru](#tsuru) e enviando para algum servidor
remoto.

Sim, você pode usar nossa plataforma como opção extra para backup de outros
projetos, porém recomendamos faça backups encriptados, mesmo que sejam
fotos de caezinhos 🐶.

### Domínios
Você pode usar seu próprio domínio pago [ou gratúito](https://freenom.com) —
recomendado caso queira servir para usuários finais! — ou optar por usar
subdomínio de `*.app.etiva.dev` que já esta apontado para cluster de servidores
da Etica.Dev.

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

## Licença da documentação ajuda.etica.dev

Domínio Público.

Favor renomear referências a Etica.Dev (em especial os guias de como conectar
ao Tsuru) caso reuse para outros usuários.
