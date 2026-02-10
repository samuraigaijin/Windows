# 🛡️ Cheat Sheet: Comandos Úteis Windows (Operação & Blue Team)

Este guia contém comandos essenciais para administração de sistemas e investigação de segurança (SOC/Blue Team) em ambientes Windows.

---

## 🔍 Informações do Sistema e Sessão
| Comando | Descrição |
| :--- | :--- |
| `hostname` | Exibe o nome da máquina. |
| `ver` | Mostra a versão exata do sistema operacional. |
| `whoami /all` | Exibe o usuário atual, privilégios e grupos a que pertence. |
| `systeminfo` | Relatório completo de hardware, SO e hotfixes instalados. |
| `qwinsta` | Lista sessões de usuários logados (RDP e console local). |
| `set` | Exibe todas as variáveis de ambiente do sistema. |

---

## 🌐 Rede e Conectividade
| Comando | Descrição |
| :--- | :--- |
| `ipconfig /all` | Detalhes completos de todas as interfaces de rede. |
| `netstat -ano` | Lista conexões ativas com o PID do processo associado. |
| `tracert <ip/host>` | Rastreia a rota dos pacotes até o destino. |
| `pathping <ip/host>` | Combina ping e tracert para identificar perda de pacotes. |
| `nslookup <host>` | Consulta registros de DNS para um domínio ou IP. |
| `arp -a` | Exibe a tabela ARP (descoberta de dispositivos na mesma rede). |
| `route print` | Exibe a tabela de roteamento IP da máquina. |
| `getmac` | Exibe os endereços físicos (MAC) das placas de rede. |

---

## ⚙️ Processos e Serviços
| Comando | Descrição |
| :--- | :--- |
| `tasklist` | Lista todos os processos em execução. |
| `taskkill /f /pid <PID>` | Finaliza um processo forçadamente pelo seu ID. |
| `net start` | Lista todos os serviços que estão rodando no momento. |
| `sc query` | Consulta o status de serviços específicos do Windows. |

---

## 📂 Arquivos, Permissões e Auditoria
| Comando | Descrição |
| :--- | :--- |
| `dir /A /S` | Lista arquivos (incluindo ocultos) em todos os subdiretórios. |
| `findstr /S /I "string" *.txt` | Busca textos específicos dentro de arquivos recursivamente. |
| `type arquivo.txt` | Exibe o conteúdo de um arquivo no terminal. |
| `icacls "C:\caminho"` | Exibe ou altera permissões de acesso (ACLs) de pastas/arquivos. |
| `powershell Get-FileHash -Algorithm SHA256 <arquivo>` | Gera o hash SHA256 para verificar integridade de ficheiros. |
| `cipher /w:C:` | Sobrescreve dados apagados para impedir recuperação forense. |

---

## 👥 Usuários e Políticas de Grupo
| Comando | Descrição |
| :--- | :--- |
| `net user` | Lista todos os usuários locais da máquina. |
| `net localgroup administrators` | Lista quem possui privilégios de administrador local. |
| `net share` | Lista todas as pastas e recursos compartilhados. |
| `gpresult /r` | Exibe as políticas de grupo (GPO) aplicadas ao usuário e máquina. |

---

## 🛠️ Monitoramento e Eventos (SOC)
| Comando | Descrição |
| :--- | :--- |
| `wevtutil qe Security /f:text /c:10 /rd:true` | Lê os últimos 10 eventos do log de Segurança. |
| `netsh advfirewall show allprofiles` | Verifica o estado atual do firewall para todos os perfis. |
