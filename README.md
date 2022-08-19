# glpi-update-version

Acessar:
````
cd /var/www/html
````
Mover o diretório glpi para glpi-old:
````
mv glpi glpi-old
````
Baixar a nova versão do glpi:
````
wget https://github.com/glpi-project/glpi/releases/download/9.5.8/glpi-9.5.8.tgz
````
Extrair o arquivo:
````
tar -zxvf glpi-9.5.8.tgz
````
Acessar o novo diretório glpi
````
cd glpi
````
Excluir os diretórios:
````
rm config files marketplace -Rf
````

//Removidos pois contem informações que não podem ser recriadas

Copiar os respectivos arquvios do glpi-old para o glpi
````
cp ../glpi-old/files . -Rf
cp ../glpi-old/config . -Rf
cp ../glpi-old/marketplace . -Rf
````
Remover o diretório plugins do glpi
````
rm plugins -Rf
````
Copiar o diretório plugins do glpi-old
````
cp ../glpi-old/plugins . -Rf
````

// Após os passos a cima, acessar o glpi web e executar a atualização na página.
(Caso persista tela em branco, geralmente erro de falta de acesso http500, 
executar os comandos):

Executar no diretório antes do GLPI /var/www/html
````
chown www-data. glpi -Rf
````
// Ao aessar o glpi habilitar os plugins que por padrão são desativados.

Remover o arquivo install.php
````
rm glpi/install/install.php
````

// Orientado pela documentação remover o diretório mas caso remova causará problemas
nas futuras atualizações. Também orientado pela comunidade que não remova o diretório.

Após tudo pronto pode remover o glpi compactado e o antigo mantido para cópia
````
rm glpi-9.5.8.tgz
rm glpi-old -Rf
````