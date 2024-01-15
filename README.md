# PhpMyadmin MkAuth

[![Mikrotik](https://www.adminer.org/static/images/logo.png)](#)
[![Mikrotik](https://blog.smsnet.com.br/wp-content/uploads/2018/06/Mk-auth-300x110.png)](#)

### Funcionalidade:
* Permite acessa o banco de dados do MKauth via webservice
* Protege o acesso de usuarios não autorizados

### Configuração no MkAuth via Putty
1 - Instale o git no seu sistema MkAuth
```sh
apt update && apt install git -s
```

2 - Instale o repositorio no seu sistema MkAuth
```sh
cd /var/www && git clone https://github.com/MKCodec/PhpMyadmin.git servidor
```
3 - Gere sua senha de Acesso
```sh
htpasswd -c /var/www/servidor/htpasswd admin
```

4 - Acesse o arquivo de configuração do apache e insira o codigo no final do arquivo
```sh
nano /etc/apache2/apache2.conf
```

```sh
<Directory /var/www/servidor>  
     Options Indexes Includes FollowSymLinks MultiViews  
     AllowOverride AuthConfig  
     Order allow,deny  
     Allow from all  
 </Directory> 
```

5 - Reinicie o Apache
```sh
service apache2 restart
```

### Acesse o PhpMyadmin no MkAuth
* Utilize o usuario admin com a senha que você criou
```sh
seudominio.com/servidor
```

### Dados de autenticação do MkAuth
| Sistema | Servidor | Usuário | Senha | Base de dados
| ------ | ------ | ------ | ------ | ------ 
| MySQL | localhost | root | vertrigo | mkradius |

