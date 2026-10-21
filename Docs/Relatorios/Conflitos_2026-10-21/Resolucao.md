# Recuperacao dos conflitos - 21/10/2026

O erro CS8300 era causado pelos marcadores de um merge entre HEAD e origin/main. A Unity nao conseguia compilar e abriu em Safe Mode. Havia tambem conflitos nas cenas e no prefab do menu: corrigir apenas os scripts deixaria esses assets invalidos.

## Resolucao

- 20 arquivos revisados e marcados como resolvidos no indice do Git.
- As duas versoes foram comparadas. Nos scripts, cenas, prefab e previas, a versao local recente preserva arremesso, cartao aleatorio, adocao do Sparrow, audio, VFX e correcoes de colisao. A outra versao corresponde ao gameplay anterior e removeria essas funcionalidades.
- Cenas e prefab recuperados integralmente do commit local validado, sem edicao manual do YAML ou execucao do gerador.
- README combina as instrucoes recebidas de instalacao com os links da documentacao recente.
- Nenhum script novo de gameplay, pacote instalado, modelo reposicionado ou asset de terceiros modificado por esta recuperacao. Alteracoes de terceiros ja presentes no merge foram preservadas.
- Cenas MainMenu/Level01_Nave_Expanded, PauseMenu e scripts proprios recuperados sao identicos ao HEAD anterior ao merge.

## Evidencias desta execucao

- Unity 6000.0.81f1 recompilou e saiu do Safe Mode.
- Gameplay_Play.txt: APROVADO em Play, com 842 movimentos reais da capsula, progressao ate a conclusao e testes de reinicio.
- Menus_Play.txt: APROVADO em Play, incluindo MainMenu, Novo Jogo, pausa, controles, reinicio, retorno e saida do Play.
- Auditoria_Cena.txt: zero scripts ausentes; jogador, EventSystem, AudioListener e HUD unicos; referencias de portas, audio, VFX e Sparrow verificadas; 1.434 renderizadores originais preservados em posicao, rotacao e escala.
- Nenhum caminho pendente retornado por git diff --name-only --diff-filter=U.
- Nenhum marcador nos arquivos ativos de Assets, Packages, ProjectSettings e documentacao, excluindo o backup intencional dos conflitos.

Esses testes nao substituem uma revisao estetica completa nem testes em build/macOS. O log registra avisos de geometria auto-intersectante do FBX Door_Left_01 de terceiros, que nao impediram a compilacao e os testes.

## Git e trabalho em equipe

O merge permanece aberto, com os conflitos resolvidos. Nao foi criado commit nem executado push. Revise as alteracoes no cliente Git, conclua o merge com um commit e envie a branch. No outro computador, atualize a mesma branch depois do envio; a correcao local nao altera automaticamente a copia do colega.

Nao selecione indiscriminadamente aceitar todas as alteracoes recebidas nos scripts ou na cena: isso removeria partes recentes do jogo. Evitem editar simultaneamente a mesma cena; dividam trabalho por scripts/prefabs e combinem quem edita a cena principal.

## Backup

`Docs/Backups/Conflitos_2026-10-21_192209` contem os arquivos antes da correcao, as versoes disponiveis dos estagios 1/2/3, o status e os hashes dos commits. Os marcadores nessa pasta sao intencionais e nao participam da compilacao.

## Arquivos em conflito recuperados

- `Assets/Prefabs/UI/PauseMenu.prefab`
- `Assets/Scenes/Level01_Nave_Expanded.unity`
- `Assets/Scenes/MainMenu.unity`
- `Assets/Scripts/Editor/Level01/Gameplay/Level01GameplaySetup.cs`
- `Assets/Scripts/Editor/Level01/Gameplay/Level01GameplayValidation.cs`
- `Assets/Scripts/Editor/Level01/Generation/Level01NaveGenerator.Expanded.cs`
- `Assets/Scripts/Editor/UI/MenuSceneSetup.cs`
- `Assets/Scripts/Runtime/Gameplay/Interaction/PlayerInteraction.cs`
- `Assets/Scripts/Runtime/Gameplay/Level01/DoorController.cs`
- `Assets/Scripts/Runtime/Gameplay/Level01/Level01GameManager.cs`
- `Assets/Scripts/Runtime/Gameplay/Level01/LevelCompleteTrigger.cs`
- `Docs/Guias/Gameplay_Nivel01.md`
- `Docs/Guias/Menus_ComoUsar.md`
- `Docs/Guias/Scripts.md`
- `Docs/Previas/Menus/01_MainMenu.png`
- `Docs/Previas/Menus/02_Controles.png`
- `Docs/Previas/Menus/03_Pausa.png`
- `Docs/README.md`
- `Docs/Relatorios/Menus/Menus_Validacao.txt`
- `README.md`
