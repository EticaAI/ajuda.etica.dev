# Olá Mundo no Etica.Dev

_TODO: criar olá mundo mais genérico (fititnt, 2019-06-25 09:12 BRT)_

```bash
# Comandos para logar
tsuru target-add https://tsuru.etica.dev -s
tsuru login seu-email@example.com
```

```bash
## Isso em devel-fititnt-bravo
mkdir -p ~/tmp/tsuru/ola-banze
cd ~/tmp/tsuru/ola-banze
echo "Au Au Banzé <?php phpinfo(); ?>" > index.php
tsuru app-create ola-banze php --team padrao
tsuru app-deploy --app ola-banze .
# Veja http://ola-banze.192.99.69.2.nip.io/
```
