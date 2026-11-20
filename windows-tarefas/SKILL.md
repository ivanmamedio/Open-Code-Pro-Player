---
name: Tarefas do Windows
description: Auxílio com operações do sistema Windows: desinstalar programas, alterar configurações, gerenciar arquivos e serviços
metadata:
  opencode/autoinvoke: false
---

# Skill: Tarefas do Windows

Esta skill orienta como auxiliar o usuário com operações do sistema Windows. Sempre que o usuário solicitar algo relacionado ao Windows (desinstalar algo, alterar configurações, gerenciar serviços, etc.), siga as diretrizes abaixo.

## 1. Antes de Executar Qualquer Ação
- Explique claramente o que o comando ou ação vai fazer.
- Peça confirmação explícita antes de comandos destrutivos ou que alteram o sistema (desinstalar programas, editar registro, excluir arquivos, desativar serviços).
- Se o comando exigir direitos de administrador, avise o usuário e explique por quê.

## 2. Desinstalar Programas
**Métodos recomendados:**
- **Configurações do Windows**: Iniciar > Configurações > Aplicativos > Aplicativos instalados > selecione o app > Desinstalar.
- **Painel de Controle**: `control appwiz.cpl` > Programa e Recursos > selecione > Desinstalar.
- **PowerShell (winget)**: `winget uninstall "<nome-do-programa>"`
- **CMD**: `wmic product where name="<nome>" call uninstall` (requer admin).

**Exemplo de comando seguro:**
```powershell
# Listar programas instalados via winget
winget list

# Desinstalar um programa (exemplo, não execute sem confirmação)
winget uninstall "NomeDoPrograma"
```

## 3. Alterar Configurações do Sistema
**Caminhos comuns no Windows 10/11:**
- **Aplicativos instalados**: Configurações > Aplicativos > Aplicativos instalados
- **Programas iniciais**: Configurações > Aplicativos > Inicializar
- **Variáveis de ambiente**: Configurações > Sistema > Sobre > Configurações avançadas do sistema > Variáveis de Ambiente
- **Gerenciador de dispositivos**: `devmgmt.msc`
- **Serviços**: `services.msc`
- **Editor de Registro**: `regedit` (use com extremo cuidado)
- **Desempenho**: `msconfig`

## 4. Comandos Úteis do PowerShell/CMD
Sempre apresente o comando e explique antes de sugerir execução:

```powershell
# Ver versão do Windows
winver

# Listar serviços
Get-Service

# Iniciar/parar um serviço (requer admin)
Start-Service "NomeDoServiço"
Stop-Service "NomeDoServiço"

# Ver processos
Get-Process

# Limpar arquivos temporários
Remove-Item "$env:TEMP\*" -Recurse -Force

# Verificar disco
chkdsk C: /f

# Instalar/desinstalar via winget
winget install <id-do-pacote>
winget uninstall <id-do-pacote>
winget upgrade --all
```

## 5. Segurança nas Operações do Windows
- Nunca sugira exclusão de arquivos do sistema (`C:\Windows`, `C:\Program Files`) sem entender o impacto.
- Antes de editar o Registro (`regedit`), sugira criar um ponto de restauração ou backup.
- Comandos que exigem "Executar como Administrador" devem ser explicitamente identificados.
- Se o usuário não tem certeza sobre uma ação, sugira criar um ponto de restauração do sistema primeiro.

## 6. Como Auxiliar o Usuário
Pergunte sempre:
1. Qual é o objetivo específico? (ex: desinstalar o X, liberar espaço, acelerar o boot)
2. O usuário tem direitos de administrador na máquina?
3. Qual versão do Windows está usando? (10 ou 11)

Forneça instruções passo a passo, com caminhos de menu e comandos de terminal quando aplicável.

## Exemplo de Resposta ao Usuário
> "Para desinstalar o programa X, você pode:
> 1. Abrir Configurações > Aplicativos > Aplicativos instalados
> 2. Procurar pelo programa X
> 3. Clicar nos três pontos (...) > Desinstalar
> 
> Ou via terminal (PowerShell como administrador):
> `winget uninstall "NomeDoPrograma"`
> 
> Deseja que eu gere o comando exato para o programa que você quer remover?"

Nunca execute comandos destrutivos no sistema do usuário sem aprovação prévia e explícita.