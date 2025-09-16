# 📘 Manual do Suporte N1
Guia prático para quem deseja iniciar e crescer na área de **Suporte Técnico Nível 1**.  
Este repositório reúne **conceitos essenciais**, **boas práticas de segurança** e **habilidades comportamentais** fundamentais para se tornar um profissional completo.

---

## 🔑 Conteúdos

### 1️⃣ Fundamentos de TI
- Hardware: componentes, manutenção e periféricos
- Sistemas Operacionais: Windows, Linux e macOS
- Redes: IP, DNS, DHCP, testes (`ping`, `tracert`)
- Protocolos: TCP/IP, HTTP/HTTPS, FTP, SMTP, IMAP/POP3

### 4️⃣ Segurança da Informação
- Boas práticas: senhas fortes, 2FA
- Antivírus e Antimalware
- Backup e restauração (local e em nuvem)
- Conscientização do usuário

### 5️⃣ Soft Skills
- Atendimento ao usuário com empatia
- Organização e gestão de tempo
- Trabalho em equipe e comunicação clara
- Postura profissional sob pressão

---

# 🖥️ Manual do Suporte N1 – Windows, Redes e Impressoras

Guia prático para profissionais de **Suporte Técnico Nível 1**.  
Este documento reúne **tarefas comuns**, **passo a passo de diagnóstico** e **conceitos fundamentais** para resolver problemas em **Windows**, **Redes** e **Impressoras**.

---

## 📌 Parte 1 – Windows (Sistemas Operacionais)

### 🎯 Objetivo
Entender como diagnosticar e resolver os problemas mais comuns no **Windows**.

### 💡 Conceitos Importantes
- **Usuário e Permissões:** Administrador vs Usuário Padrão  
- **Serviços:** Programas que rodam em segundo plano (ex.: Spooler de impressão)  
- **Drivers:** Software que permite que o hardware funcione corretamente  
- **Atualizações:** Corrigem falhas e aumentam a segurança

### 🗂️ Tarefas Comuns no Windows

| Problema                   | Ferramentas / Caminho                            | Ação Recomendada                                                                 |
|------------------------------|----------------------------------------------------|-----------------------------------------------------------------------------------|
| Windows lento                | **Gerenciador de Tarefas** (Ctrl+Shift+Esc)      | Identificar processos que consomem memória/CPU e finalizar se necessário.         |
| Sem acesso à rede            | **Painel de Controle > Rede e Internet**         | Verificar adaptador de rede, status da conexão.                                   |
| Programas não abrindo        | **Configurações > Aplicativos**                  | Reparar ou reinstalar aplicativo.                                                 |
| Tela azul (BSOD)             | **Visualizador de Eventos**                      | Checar logs para identificar erro (drivers, memória, hardware).                   |
| Impressora não imprime       | **Configurações > Dispositivos > Impressoras**   | Verificar fila, reiniciar spooler, reinstalar driver.                             |

### ✅ Passo a Passo – Diagnóstico Geral no Windows
1. **Confirmar o Sintoma:** Perguntar ao usuário o que aconteceu, quando começou e se mudou algo recentemente.  
2. **Verificar Rede:** Ícone de rede (canto inferior direito) → Testar navegação ou `ping 8.8.8.8`.  
3. **Checar Drivers:** `Gerenciador de Dispositivos` → procurar avisos amarelos.  
4. **Testar com Usuário Diferente:** Ver se o problema é do perfil ou do sistema.  
5. **Atualizações:** `Configurações > Windows Update` → instalar pendentes.  
6. **Log de Eventos:** `eventvwr.msc` → verificar falhas críticas.  
7. **Restaurar Sistema:** Ponto de restauração para estado anterior, se necessário.

---

## 🌐 Parte 2 – Redes

### 🎯 Objetivo
Diagnosticar falhas de **conexão de internet e rede local**.

### 💡 Conceitos Básicos
- **IP:** Identificador do dispositivo na rede  
- **Gateway:** Saída para acessar a internet (normalmente o roteador)  
- **DNS:** Tradução de nomes (ex.: google.com → IP)  
- **DHCP:** Entrega automática de IP

### 🗂️ Tarefas de Rede

| Problema                           | Comando/Ferramenta                           | Ação Recomendada                                                                  |
|--------------------------------------|-----------------------------------------------|------------------------------------------------------------------------------------|
| Sem internet                          | `ping 8.8.8.8`                               | Se não responder, verificar cabo, Wi-Fi ou roteador.                               |
| Perda de IP                           | `ipconfig` (Windows) / `ifconfig` (Linux)    | Se não houver IP, rodar `ipconfig /renew` ou checar DHCP.                           |
| DNS não resolve sites                 | `nslookup google.com`                        | Se falhar, configurar DNS manual (ex.: 8.8.8.8).                                    |
| Conexão lenta                          | Speedtest, `ping` para roteador              | Verificar latência, interferência Wi-Fi ou largura de banda.                        |
| Rede interna inacessível (pastas, etc)| `ping [IP do servidor]`                      | Testar rota, checar permissões de compartilhamento.                                 |

### ✅ Passo a Passo – Diagnóstico de Rede
1. **Checar Conexão Física:** Cabo conectado ou Wi-Fi ativo.  
2. **Obter IP:** Abrir CMD → `ipconfig`.  
   - Se não houver IP, rodar `ipconfig /release` e `ipconfig /renew`.  
3. **Testar Gateway:** `ping [gateway]` (ex.: 192.168.0.1).  
4. **Testar Internet:** `ping 8.8.8.8` (Google).  
   - Se OK, mas sites não abrem → problema de **DNS**.  
5. **DNS Manual:** Definir 8.8.8.8 (Google) ou 1.1.1.1 (Cloudflare).  
6. **Verificar Firewall/VPN:** Desativar temporariamente para testar.  
7. **Reiniciar Modem/Roteador**, se necessário.

---

## 🖨️ Parte 3 – Impressoras

### 🎯 Objetivo
Corrigir problemas de impressão em impressoras **locais (USB)** ou **de rede**.

### 💡 Conceitos Importantes
- **Driver:** Necessário para comunicação entre PC e impressora  
- **Spooler de Impressão:** Serviço do Windows que gerencia a fila de impressão  
- **IP Fixo:** Em impressoras de rede, evita perda de conexão

### 🗂️ Tarefas em Impressoras

| Problema                        | Ferramenta / Local                             | Ação Recomendada                                                                |
|----------------------------------|--------------------------------------------------|----------------------------------------------------------------------------------|
| Impressora não aparece no Windows| **Configurações > Dispositivos > Impressoras**  | Adicionar manualmente ou reinstalar driver.                                      |
| Fila de impressão travada         | **Serviços do Windows** (`services.msc`)        | Reiniciar serviço **Spooler de Impressão**.                                      |
| Impressão borrada ou falha física | Painel da impressora                            | Limpar cabeçote, verificar tinta/toner, calibrar.                                |
| Impressora de rede não imprime    | CMD (`ping [IP da impressora]`)                 | Se não responder, checar cabo, IP ou configurar IP fixo.                         |
| Impressão lenta                   | Propriedades da Impressora                      | Alterar tipo de driver (PCL/PS), reduzir qualidade de impressão.                 |

### ✅ Passo a Passo – Diagnóstico de Impressora
1. **Checar Conexão Física:**  
   - USB: Cabo bem conectado.  
   - Rede: Cabo no switch/roteador ou Wi-Fi conectado.  
2. **Verificar Status no Windows:**  
   - Configurações > Impressoras → ver se está como **Padrão**.  
3. **Limpar Fila de Impressão:**  
   - Painel de Controle → Dispositivos → Fila → **Cancelar todos os documentos**.  
4. **Reiniciar Spooler:**  
   - Abrir `services.msc` → Serviço **Spooler de Impressão** → Reiniciar.  
5. **Testar IP (se de rede):**  
   - `ping [IP da impressora]`.  
6. **Reinstalar Driver:**  
   - Baixar do site oficial do fabricante.  
7. **Teste de Impressão:**  
   - Imprimir página de teste do Windows.

---

## 🔑 Dicas de Ouro (Checklist Rápido)
✅ Sempre **perguntar ao usuário** se algo mudou antes do problema (atualizações, cabos, quedas de energia).  
✅ **Documentar cada passo** no sistema de tickets (ex.: Tiflux).  
✅ **Reiniciar equipamentos** é um dos primeiros testes – muitas falhas são temporárias.  
✅ Usar **ferramentas nativas** (CMD, Painel de Controle, Gerenciador de Dispositivos) antes de instalar softwares de terceiros.

---

### 🚀 Contribuições
Quer ajudar a melhorar este manual?  
- Faça um **fork** do repositório  
- Crie uma nova branch  
- Envie um **pull request** com melhorias ou novos conteúdos


## 🚀 Objetivo
Criar um **caminho de aprendizado** para quem está começando no Suporte N1, facilitando a entrada no mercado e fortalecendo a base técnica e comportamental.


