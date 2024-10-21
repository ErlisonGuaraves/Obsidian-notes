
Antes de testar o <font color="#00b050">Nginx</font>, o software de <font color="#0070c0">firewall</font> precisa ser configurado para permitir o acesso ao serviço. O <font color="#00b050">NGINX</font> se registra como um serviço `ufw`após a instalação, tornando mais fácil permitir o acesso ao <font color="#00b050">Nginx</font>.

Liste as configurações do aplicativo que `ufw`você sabe trabalhar digitando:

```bash
sudo ufw app list
```

Você deverá obter uma lista dos perfis de aplicativos:

```
Output
Available applications:
  Nginx Full
  Nginx HTTP
  Nginx HTTPS
  OpenSSH
```

Você pode ativar isso digitando:

```bash
sudo ufw allow 'Nginx HTTP'
```

Você pode verificar a alteração digitando:

```bash
sudo ufw status
```

A saída indicará qual tráfego <font color="#ff0000">HTTP</font> é permitido:

```
Output
Status: active
To                         Action      From
--                         ------      ----
OpenSSH                    ALLOW       Anywhere
Nginx HTTP                 ALLOW       Anywhere
OpenSSH (v6)               ALLOW       Anywhere (v6)
Nginx HTTP (v6)            ALLOW       Anywhere (v6)
```