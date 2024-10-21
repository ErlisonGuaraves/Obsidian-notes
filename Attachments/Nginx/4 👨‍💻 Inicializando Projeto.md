## Instalando Dependências

1. Instale o Vite globalmente, se ainda não tiver feito:
    
    ```
    npm install -g create-vite
    
    ```
    
2. Crie um novo projeto React usando Vite:
    
    ```
    create-vite my-react-app
    
    ```
    
3. Navegue até o diretório do seu projeto e inicie o servidor de desenvolvimento:
    
    ```
    cd my-react-app
    npm run dev
    
    ```
    
4. Quando estiver pronto para implantar, construa seu site para produção:
    
    ```
    npm run build
    
    ```
    

Isso criará uma pasta `dist` com os arquivos estáticos do seu aplicativo React:

![Untitled](Attachments/Nginx/Inicializando%20Projeto/Untitled.png)

### **Configuração do Nginx:**

Agora, vamos configurar o Nginx para servir o seu aplicativo React:

1. Crie um novo arquivo de configuração para o seu site dentro do diretório `/etc/nginx/sites-available/`. Por exemplo, `meusite.com.conf`.
2. Abra o arquivo de configuração em um editor de texto como Nano ou Vim e adicione o seguinte conteúdo:
    
    ```
    server {
        listen 80;
        server_name meusite.com www.meusite.com; # substitua pelo seu domínio
    
        root /caminho/para/o/seu/site/react/dist; # substitua pelo caminho correto para o diretório de construção do seu site React
    
        index index.html index.htm;
    
        location / {
            try_files $uri $uri/ /index.html;
        }
    }
    
    ```
    
    Certifique-se de substituir `meusite.com` pelo seu domínio e `/caminho/para/o/seu/site/react/dist` pelo caminho correto para o diretório de construção do seu site React.
    
3. Crie um link simbólico do arquivo de configuração do site de `sites-available` para `sites-enabled`:
    
    ```
    sudo ln -s /etc/nginx/sites-available/meusite.com.conf /etc/nginx/sites-enabled/
    ```
    
4. Teste a configuração do Nginx para verificar se há erros:
    
    ```
    sudo nginx -t
    ```
    
5. Recarregue o Nginx para aplicar as alterações:
    
    ```
    sudo systemctl reload nginx
    ```
    

**4. Acesso ao Site:**

Se tudo estiver configurado corretamente, agora você deve ser capaz de acessar seu site React através do domínio especificado no navegador.