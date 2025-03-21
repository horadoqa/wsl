# Comandos

Para verificar a versão do **WSL** (Windows Subsystem for Linux) no seu sistema Windows, você pode usar o PowerShell ou o Prompt de Comando. Aqui estão os passos:

### 1. **Usando o PowerShell ou Prompt de Comando**:
   Abra o **PowerShell** ou **Prompt de Comando** e execute o seguinte comando:

   ```powershell
   wsl --list --verbose
   ```

   ou, de forma mais compacta:

   ```powershell
   wsl -l -v
   ```

   Isso vai mostrar uma lista de distribuições do Linux instaladas no WSL, junto com a versão do WSL (1 ou 2) que cada uma está usando.

### 2. **Usando o comando `wsl --status` (informações detalhadas)**:
   Você também pode usar o comando abaixo para obter informações detalhadas sobre o estado do WSL no seu sistema:

   ```powershell
   wsl --status
   ```

   Esse comando mostrará a versão padrão do WSL (se é a versão 1 ou 2), bem como outras configurações, como o kernel em uso.

### Exemplos de saída:
- Se você estiver usando o **WSL 1**, a saída pode ser algo como:
  
  ```bash
  NAME      STATE           VERSION
  * Ubuntu    Running         1
  ```

- Se você estiver usando o **WSL 2**, a saída pode ser parecida com:

  ```bash
  NAME      STATE           VERSION
  * Ubuntu    Running         2
  ```

### Como mudar a versão do WSL:
Se precisar mudar a versão do WSL de 1 para 2 ou vice-versa, pode usar o comando abaixo:

- Para mudar a versão de uma distribuição específica para o WSL 2:

  ```powershell
  wsl --set-version <DistroName> 2
  ```

- Para mudar para a versão 1:

  ```powershell
  wsl --set-version <DistroName> 1
  ```

---

Para reiniciar o WSL, incluindo a distribuição Ubuntu (ou qualquer outra distribuição), você pode usar o PowerShell ou o Prompt de Comando. Aqui estão as etapas:

### 1. **Usar o comando `wsl --shutdown` (recomendo esta opção)**
Este comando encerra todas as distribuições WSL e reinicia o subsistema. É o método mais simples e eficaz:

```powershell
wsl --shutdown
```

Após executar o comando, ao iniciar novamente qualquer distribuição WSL (por exemplo, **Ubuntu**), o WSL será reiniciado.

### 2. **Verificar o serviço correto**
Se você quiser reiniciar o serviço do **WSL**, o nome do serviço pode ser diferente dependendo da versão do Windows e do WSL. Em vez de `LxssManager`, você pode tentar o serviço `wslservice`:

```powershell
Restart-Service wslservice
```

Se o erro persistir, isso significa que o serviço pode não estar disponível ou ser necessário reiniciar o computador para reiniciar completamente o WSL.

### 3. **Reiniciar o computador**
Se as opções acima não funcionarem, uma forma simples de reiniciar o WSL é reiniciar o computador, o que deve reiniciar todos os serviços do WSL automaticamente.

### Conclusão
A solução mais prática é usar o comando `wsl --shutdown`, que reinicia o subsistema WSL de maneira eficaz. Caso não funcione, reiniciar o computador pode ser a maneira mais rápida de corrigir o problema.
