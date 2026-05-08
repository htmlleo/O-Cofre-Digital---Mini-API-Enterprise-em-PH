O Cofre Digital — Mini API em PHP
📌 Visão geral

O Cofre Digital é um sistema em PHP feito para armazenar anotações e segredos de usuários de forma segura. Ele funciona como uma API simples com autenticação e controle de acesso.

O projeto foi desenvolvido com foco em segurança básica (Security by Design) e organização em camadas, usando uma estrutura parecida com MVC.

O sistema também foi pensado para simular um ambiente de auditoria de segurança, onde pode ser testado tanto para defesa quanto para tentativa de exploração.

⚙️ Funcionalidades
Cadastro de usuários
Login e logout com sessão PHP
Criação de segredos (anotações privadas)
Listagem e visualização de segredos do próprio usuário
Isolamento de dados por usuário (cada um vê apenas o seu)
🧰 Tecnologias usadas
PHP 8+
MySQL
HTML, CSS e JavaScript
XAMPP
Comunicação via JSON
📁 Estrutura do projeto
cofre-digital/
│
├── api/            → Endpoints da API (login, registro, segredos)
├── core/           → Conexão com banco, segurança e respostas JSON
├── models/         → Regras de usuários e segredos
├── config/         → Configurações do sistema
├── database/       → Script do banco de dados
├── public/         → Interface (HTML, CSS e JS)
🔐 Segurança aplicada
Senhas com password_hash e password_verify
Uso de PDO com queries preparadas (evita SQL Injection)
Validação básica de entrada
Sessão PHP para login
Acesso protegido por usuário logado
Cada usuário só acessa seus próprios dados
Respostas sempre em JSON
🚀 Como rodar
Colocar o projeto dentro da pasta htdocs do XAMPP
Criar banco de dados cofre_digital
Importar o arquivo database/schema.sql
Ajustar config/config.php se necessário
Iniciar Apache e MySQL
Acessar:
http://localhost/cofre-digital/public/
📡 API (resumo)
🔑 Login e registro
POST /api/AuthController.php?action=register
POST /api/AuthController.php?action=login
POST /api/AuthController.php?action=logout
🔐 Segredos
POST /api/SecretController.php?action=create
GET /api/SecretController.php?action=list
GET /api/SecretController.php?action=show&id=1
🧠 Observações

O sistema foi feito de forma modular, separando lógica de autenticação, banco de dados e regras de segurança, para facilitar manutenção e testes.

Ele também permite simular testes de segurança, onde é possível verificar falhas ou tentar proteger melhor a aplicação.

👨‍💻 Autor

Leonardo Estevão Alves
Registro Acadêmico: 00250458
