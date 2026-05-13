# Higgsfield - status e uso no projeto

## Status encontrado

Higgsfield CLI esta disponivel via:

```powershell
C:\Users\Arthu\AppData\Roaming\npm\higgsfield.cmd
```

Conta autenticada no momento da auditoria:

```text
loginia02@gmail.com — creator plan
```

Nano Banana Pro esta disponivel como:

```text
job_set_type: nano_banana_2
display_name: Nano Banana Pro
```

Parametros aceitos:

- `--prompt`
- `--aspect_ratio`
- `--resolution`
- `--image` para referencia visual
- `--wait`

Aspect ratios relevantes:

- `4:5`
- `1:1`

Resolucao:

- `2k`

## Observacoes

- `npx higgsfield --help` e `npm view higgsfield` foram bloqueados pela politica de execucao do PowerShell.
- `.cursor/mcp.json` e `$HOME/.cursor/mcp.json` nao foram encontrados.
- Nenhum token foi exibido ou salvo.
- Nao foi feito login novo.

## Comandos base para gerar criativos

```powershell
$hf = 'C:\Users\Arthu\AppData\Roaming\npm\higgsfield.cmd'
$logo = 'C:\Users\Arthu\OneDrive\Área de Trabalho\MusclePrime Brasil\MusclePrimeBrasil\muscleprime-brasil.catalog.kyte.site\assets\brand\muscleprime-logo-variation-3-premium-pharma.png'
$screenshot = 'C:\Users\Arthu\OneDrive\Área de Trabalho\MusclePrime Brasil\MusclePrimeBrasil\muscleprime-brasil.catalog.kyte.site\docs\creative\meta-ads-muscleprime\site-current-screenshot.png'

& $hf generate create nano_banana_2 `
  --prompt "<PROMPT_4x5>" `
  --image $logo `
  --image $screenshot `
  --aspect_ratio "4:5" `
  --resolution "2k" `
  --wait `
  --wait-timeout "20m"

& $hf generate create nano_banana_2 `
  --prompt "<PROMPT_1x1>" `
  --image $logo `
  --image $screenshot `
  --aspect_ratio "1:1" `
  --resolution "2k" `
  --wait `
  --wait-timeout "20m"
```

## Motion preview

Para motion previews, usar o primeiro frame gerado como `--start-image` em modelo de video disponivel no Higgsfield, mantendo:

- 6 a 8 segundos.
- Sem audio obrigatorio.
- Movimento de camera suave.
- Sem texto embaralhado ou reescrito.
- Sem novas palavras geradas.
- Sem claims medicos.

Antes de gerar video, confirmar o modelo com:

```powershell
& $hf model list --video
```
