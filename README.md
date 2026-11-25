# shell-runtime

Pacote shell-runtime da distribuição ThinkIac.

Repositório: https://github.com/ThinkIac/shell-runtime.

## Uso no ThinkIac

Este pacote foi extraído de `packages/shell/runtime`. Preserve a identidade `shell-runtime` do manifest ao instalá-lo em um workspace Lógos. Views, rotas, ferramentas e hooks são descobertos pelo runtime e dependem dos provedores correspondentes. Esta extração publica o código atual; não converte JavaScript para LógosType nem implementa instalação por perfil.

## Dependências e validação

Consulte `package.json` e os imports para as capacidades exigidas do host.

O pacote não declara scripts npm de build/teste. Os testes existentes acompanham o fonte; a composição completa requer o host ThinkIac.

## Segurança e dados locais

Credenciais devem ser configuradas no ambiente de destino. Não acompanham esta extração bancos, sessões, uploads, perfis pessoais, arquivos `.env`, caches ou backups. As exclusões foram registradas em relatório externo à publicação. Configure segredos pelo host, sem incluí-los em commits.


## Registros encontrados no código

- `hook`: `aura:add_provider`, `aura:apps:list`, `aura:apps:views`, `aura:edit_provider`, `aura:get_providers`, `aura:remove_provider`, `aura:set_failover`, `aura:system:battery`, `aura:system:status`, `aura:wireless:connect`, `aura:wireless:disconnect`, `aura:wireless:scan`, `aura:wireless:status`, `device:mobile.apps.inventory.updated`, `getVolumeStatus`, `listAudioDevices`, `load_settings`, `save_settings`, `setSystemVolume`, `switchAudioDevice`.
- `router`: `apps/availability`, `apps/list`, `apps/mobile/inventory`, `apps/mobile/launch`, `apps/view-visibility`, `audio/devices`, `audio/status`, `audio/switch`, `audio/volume`, `connect`, `runtime/dispatch-event`, `settings/failover`, `settings/providers`, `settings/providers/:name`, `si/battery`, `si/system-status`, `wireless/current`, `wireless/disconnect`, `wireless/scan`.
- `tool`: `add_provider`, `connectToNetwork`, `disconnectNetwork`, `edit_provider`, `getActiveApps`, `getAudioStatus`, `getCurrentWirelessConnection`, `get_battery`, `get_providers`, `get_system_status`, `listAudioDevices`, `remove_provider`, `scanAvailableNetworks`, `setSystemVolume`, `set_failover`, `switchAudioDevice`.

A lista é um inventário estático e pode incluir registros em testes; não garante disponibilidade sem os provedores do host.

Há imports relativos para diretórios superiores. A instalação isolada e a composição por perfil precisam resolver esses vínculos antes de remover a cópia da base.

