# 🛡️ Auditoria de Segurança com Kali Linux e Medusa

### *Simulação de ataques de força bruta e técnicas de enumeração em ambiente controlado (DIO Challenge)*

Este repositório contém minha documentação do desafio proposto pela DIO,
envolvendo utilização do **Kali Linux**, **Medusa**, **Metasploitable
2** e **DVWA**, para estudo de ataques de força bruta, password spraying
e análise de superfície de ataque --- sempre em **ambiente seguro e
autorizado**.

> ⚠️ **Aviso Ético:**\
> Todas as práticas descritas aqui foram realizadas **exclusivamente em
> ambiente controlado**, com máquinas virtuais isoladas e propósito
> educacional.\
> Nunca realize testes de segurança sem autorização formal do
> proprietário do sistema.

------------------------------------------------------------------------

# 📖 **Objetivo do Projeto**

O objetivo deste estudo é:

-   Configurar um laboratório seguro utilizando VirtualBox, Kali Linux e
    Metasploitable 2.\
-   Simular cenários de ataque com a ferramenta **Medusa**,
    compreendendo seus modos, parâmetros e limitações.\
-   Testar vulnerabilidades em serviços como **FTP**, **formulários web
    vulneráveis (DVWA)** e **SMB**.\
-   Criar wordlists simples para simulação.\
-   Documentar resultados e propor medidas de prevenção.

------------------------------------------------------------------------

# 🖥️ **Arquitetura do Laboratório**

    +----------------------+         +------------------------+
    |      Kali Linux      | <-----> |   Metasploitable 2     |
    | (Máquina Atacante)   |         | (Máquina Vulnerável)   |
    +----------------------+         +------------------------+
            Rede Interna (Host-Only - Isolada)

------------------------------------------------------------------------

# 🧪 **Cenários de Teste Realizados**

## 1. 🔐 Teste de Força Bruta em Serviço FTP

-   Identificação do serviço ativo\
-   Construção de wordlist minimalista\
-   Teste de repetidas autenticações contra o serviço\
-   Análise das respostas, comportamento do servidor e registros de log

------------------------------------------------------------------------

## 2. 🌐 Teste de Automação em Formulário Web (DVWA)

-   Avaliação dos níveis Low / Medium / High\
-   Observação do impacto de validações mais fracas\
-   Teste do comportamento do formulário sob tentativas automatizadas

------------------------------------------------------------------------

## 3. 🧱 Password Spraying + Enumeração de Usuários em SMB

-   Identificação do serviço SMB\
-   Enumeração controlada de possíveis nomes de usuários\
-   Aplicação de password spraying com uma mesma senha para múltiplos
    usuários

------------------------------------------------------------------------

# 🗂️ **Wordlists Utilizadas**

Exemplo de wordlist de usuários:

    admin
    user
    guest
    test

Exemplo de wordlist de senhas:

    123456
    admin
    password
    qwerty

------------------------------------------------------------------------

# 📋 **Principais Aprendizados**

-   Serviços legados podem ser exploráveis sem políticas adequadas.\
-   Pequenas mudanças (CAPTCHA, limites de tentativa, senhas fortes) são
    extremamente efetivas.\
-   Ferramentas como Medusa demonstram a importância de boas práticas de
    autenticação.

------------------------------------------------------------------------

# 🛡️ **Medidas de Mitigação**

## Para FTP:

-   Usar SFTP/FTPS\
-   Limitar tentativas\
-   Senhas fortes\
-   Remover usuários padrão

## Para Web:

-   CAPTCHA\
-   MFA\
-   Hash seguro\
-   Rate limiting

## Para SMB:

-   Remover serviços legados\
-   Políticas de senha forte\
-   Auditoria

------------------------------------------------------------------------

# 📝 **Conclusão**

O desafio demonstra, na prática, como vulnerabilidades simples podem ser
exploradas e como medidas de mitigação protegem serviços e usuários.
