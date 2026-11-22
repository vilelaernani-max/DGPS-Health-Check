# DGPS Health Check

Ferramenta web de aferição de DGPS/GNSS a partir de log NMEA (GGA) ou ASCII; roda como site estático.

## Estrutura
- `CLAUDE.md`
- `LEIA-ME.txt`
- `README.md`
- `index.html`
- `lib/`

## Regras (definidas pelo usuário)
1. Sempre responder em português.
2. Ao alterar `index.html`, atualizar o GitHub (commit e push) e avisar.
3. Ao alterar o `CLAUDE.md`, fazer commit e push e avisar.

As regras acima valem só para `index.html` e `CLAUDE.md`. Em qualquer outro arquivo, não fazer commit nem push sem o usuário pedir.

## Como trabalhar aqui
- Ler o `README.md` antes de mexer.
- Comandos de shell passam pelo RTK; se a saída vier estranha, repetir com `rtk proxy <comando>`.

## Registro no MONITOR DEV (rotina de cada entrega)
Regra do Ernani de 20/11/2026 (guia completo: `docs/GUIA-MONITOR-DEV.md` no JERVIS-CRADIO). O MONITOR DEV é o artefato https://claude.ai/artifact/LMbjFynbZbaHuuHttSE33u; grava-se com a ferramenta ArtifactData. **Id deste projeto: `dgps-health-check`.**

Ao terminar cada entrega publicada:
1. Ler `projetos/dgps-health-check` e guardar a `version` lida.
2. Criar na coleção `versoes` um documento com id no formato `dgps-health-check-v1-0-0` (número da versão com hífens) e os campos `projeto_id: "dgps-health-check"`, `numero`, `data` (AAAA-MM-DD, hora local), `titulo`, `notas` (uma linha por mudança, começando com "- "), `feedback_ids: []`, `roadmap_ids: []`, `criado_em` e `atualizado_em` (data e hora ISO).
3. Fazer **update (nunca set)** de `projetos/dgps-health-check` com `if_version`: `versao` com o novo número e `atualizado_em`. Se mudaram, também `app_url`, `site_url`, `video_url`, `repositorio_url`, `descricao` ou `tecnologias`. Se a gravação falhar por versão, ler de novo e refazer.
4. Mudança de fase: update de `status` (`ideia`, `em_desenvolvimento`, `em_validacao`, `producao`, `pausado`) e um item `{de, para, em, obs}` no fim de `historico`.
5. Avisar o Ernani do que foi registrado.

Também na rotina: quando alguém testa, uma validação e os erros em Feedbacks; quando se planeja o próximo passo, um item no Roadmap; quando se paga algo, um gasto (pelo app). Uma vez por mês, conferir a situação do projeto na seção 5 do guia.

## Código enxuto (regra do Ernani de 22/11/2026)
- Menor mudança completa: precisa existir? Já existe no app (função, componente, padrão)? O navegador resolve? Dependência nova nunca por poucas linhas, e só com o sim do Ernani.
- Cada linha mudada liga-se ao pedido: nada de "melhorar" código vizinho, comentário ou formatação; siga o estilo do arquivo.
- Código morto encontrado é apontado no relatório, não apagado. Apague só o que a sua mudança deixou sem uso.
- Saiu grande demais (200 linhas onde 50 bastam)? Reescreva menor antes de entregar.
