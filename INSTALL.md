# 📦 Manual de Instalação e Configuração

Este documento descreve o processo técnico detalhado para instalar o sistema **Missão**.

## 📋 Pré-requisitos
Certifique-se de que seu ambiente atenda aos seguintes requisitos:
*   **PHP:** Versão 8.0 ou superior.
*   **Banco de Dados:** MySQL ou MariaDB.
*   **Extensões PHP:** `pdo`, `pdo_mysql`.
*   **Composer:** Versão 2.x (Para instalação de dependências).

---

## 🚀 Passo a Passo da Instalação

### 1. Preparação (Ambiente Local)
O sistema utiliza bibliotecas modernas que são gerenciadas pelo **Composer**. Antes de enviar os arquivos para a hospedagem, você precisa preparar o pacote.

1.  Baixe os arquivos do projeto para o seu computador.
2.  Abra o terminal na pasta raiz do projeto.
3.  Execute o comando para instalar as dependências:
    ```bash
    composer install --no-dev --optimize-autoloader
    ```
    > **Nota:** Isso irá gerar uma pasta chamada `vendor` na raiz do projeto, contendo todas as bibliotecas necessárias (como gerador de PDF, UUIDs, etc).

### 2. Upload para Hospedagem (Deploy)
Agora que o projeto está "compilado" com suas dependências:

1.  Acesse o gerenciador de arquivos da sua hospedagem (cPanel, FTP, FileZilla).
2.  Envie **TODOS** os arquivos e pastas do projeto para a pasta pública do servidor (geralmente `public_html` ou `www`).
    *   ⚠️ **Importante:** Certifique-se de incluir a pasta `vendor` que foi gerada no passo anterior. Sem ela, o sistema não funcionará.

#### 💡 Alternativa para Usuários Avançados (SSH)
Se você tem acesso SSH ao servidor e prefere não fazer upload da pasta `vendor` (que pode ser grande):
1.  Faça upload de todos os arquivos, **exceto** a pasta `vendor`.
2.  Acesse o servidor via SSH.
3.  Navegue até a pasta onde enviou os arquivos.
4.  Rode o comando: `composer install --no-dev`.

### 3. Configuração do Banco de Dados
Antes de rodar o instalador, você precisa criar um banco de dados vazio na sua hospedagem:

1.  Acesse o painel de controle da sua hospedagem (cPanel, DirectAdmin, etc.).
2.  Localize a seção de **Banco de Dados MySQL**.
3.  Crie um novo Banco de Dados (ex: `missao_db`).
4.  Crie um Usuário e Senha para o banco.
5.  **Dê permissão total** (ALL PRIVILEGES) para esse usuário acessar o banco criado.
6.  Anote o **Nome do Banco**, **Usuário** e **Senha**.

### 4. Instalação Web
Com os arquivos no lugar e o banco criado, finalize a configuração pelo navegador:

1.  Acesse o endereço do seu site (ex: `http://seu-dominio.com/install/`).
2.  O sistema fará uma verificação automática de requisitos:
    *   Versão do PHP
    *   Extensões necessárias
    *   Permissões de escrita
    *   Dependências (Pasta `vendor`)
3.  Se tudo estiver **OK**, clique em "Iniciar Instalação".
4.  Informe os dados do banco de dados que você criou no Passo 3.
5.  Crie a conta do Administrador Master.

---

---

## 🔧 Manutenção e Backups

### Reinstalação do Sistema
O instalador é bloqueado automaticamente após a primeira configuração por motivos de segurança. Se você precisar reinstalar o sistema do zero:

1.  Acesse os arquivos do sistema na sua hospedagem.
2.  Localize e **exclua** o **arquivo de configuração de ambiente** gerado na raiz.
    *   *Geralmente é um arquivo oculto contendo as credenciais do banco.*
3.  Acesse novamente a URL `/install` no navegador.
    *   ⚠️ **Cuidado:** Isso permitirá reconfigurar o banco de dados, mas não apaga os dados existentes no banco a menos que você sobrescreva as tabelas manualmente.

### Backups e Restauração
Recomendamos fortemente que você realize backups periódicos usando a ferramenta interna do sistema (`Admin > Backups`).

#### Como Restaurar um Backup
Caso precise recuperar os dados usando um arquivo gerado pelo sistema:
1.  **Descompacte** o arquivo `.zip` que você baixou.
2.  Acesse o **phpMyAdmin** ou a ferramenta de gestão de banco de sua hospedagem.
3.  Selecione o banco de dados onde o sistema está instalado.
4.  Use a opção **Importar** e selecione o arquivo `.sql` extraído.
    *   Isso irá recriar a estrutura e restaurar os dados como estavam no momento do backup.
