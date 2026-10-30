# 🚦 RedLightGreenLight

Plugin de minigame para Minecraft 1.8.9 inspirado na brincadeira *Batatinha Frita 1, 2, 3*.

Os jogadores atravessam uma arena enquanto a boneca alterna entre **GREEN LIGHT** e **RED LIGHT**. Avançar durante o sinal vermelho resulta em eliminação; vence quem alcançar a chegada ou permanecer na partida, conforme as regras configuradas.

> Um sinal verde para avançar. Um sinal vermelho para parar. 🚦

---

## 🎮 Sobre o projeto

O RedLightGreenLight foi especificado para servidores Spigot 1.8.9, com Java e NMS `v1_8_R3`. A proposta é oferecer partidas em arenas configuráveis, com alternância de sinais, eliminação por movimento durante o vermelho e identificação de vencedores.

**Status:** este repositório ainda não contém a implementação do plugin. As funcionalidades, os comandos e as permissões abaixo descrevem o escopo definido para o projeto; não representam recursos já compilados ou verificados.

### ⚙️ Funcionalidades previstas

- Gerenciamento de arenas e partidas
- Estados de partida: `WAITING`, `STARTING`, `GREEN`, `RED` e `ENDING`
- Entrada e saída de jogadores, limite de participantes e contagem regressiva
- Alternância dos sinais com durações configuráveis
- Detecção de movimento durante o sinal vermelho e eliminação
- Linha de chegada e registro de colocação dos jogadores
- Boneca controlada por NMS da versão `v1_8_R3`
- Modo espectador para jogadores eliminados
- Scoreboard, mensagens, sons e efeitos
- Persistência da configuração das arenas em YAML

---

## 📋 Requisitos

- Servidor **Spigot 1.8.9**
- Java compatível com a versão de Spigot utilizada
- Gradle com Kotlin DSL para compilar o projeto (`build.gradle.kts`)
- NMS `v1_8_R3`, incluído na implementação do plugin

O projeto foi especificado sem dependências de plugins externos e sem APIs Bukkit de versões posteriores à 1.8.9.

---

## 💻 Comandos

O comando principal é `/rl`. Os comandos abaixo fazem parte da especificação do projeto.

| Comando | Descrição | Acesso |
| --- | --- | --- |
| `/rl` | Exibe a ajuda disponível para o usuário | Todos |
| `/rl join <arena>` | Entra em uma arena disponível | Todos |
| `/rl leave` | Sai da partida ou do modo espectador | Todos |
| `/rl start <arena>` | Inicia uma partida manualmente | `redlight.admin.start` |
| `/rl stop <arena>` | Encerra uma partida ativa | `redlight.admin.stop` |
| `/rl create <arena>` | Cria uma arena | `redlight.admin.create` |
| `/rl delete <arena> confirm` | Confirma a exclusão de uma arena | `redlight.admin.delete` |
| `/rl setspawn <arena>` | Define o ponto de spawn dos participantes | `redlight.admin.setup` |
| `/rl setfinish <arena>` | Define a chegada da arena | `redlight.admin.setup` |
| `/rl setdoll <arena>` | Define a posição da boneca | `redlight.admin.setup` |
| `/rl setlobby <arena>` | Define o lobby de retorno | `redlight.admin.setup` |
| `/rl reload` | Recarrega as configurações | `redlight.admin.reload` |
| `/rl list` | Lista arenas e seus estados | `redlight.admin.list` |

Os comandos que definem posições precisam ser executados por um jogador. A especificação também prevê sugestões de tab completion para os subcomandos.

---

## 🔐 Permissões

| Permissão | Descrição |
| --- | --- |
| `redlight.admin` | Acesso administrativo geral |
| `redlight.admin.start` | Iniciar partidas |
| `redlight.admin.stop` | Encerrar partidas |
| `redlight.admin.create` | Criar arenas |
| `redlight.admin.delete` | Excluir arenas |
| `redlight.admin.setup` | Configurar posições das arenas |
| `redlight.admin.reload` | Recarregar configurações |
| `redlight.admin.list` | Listar arenas |

A especificação define `/rl`, `/rl join` e `/rl leave` como comandos disponíveis a jogadores sem permissões administrativas.

---

## 🛠️ Configuração

A estrutura planejada utiliza três arquivos YAML:

- `config.yml` — limites de jogadores, contagem regressiva, tempos dos sinais, sons, efeitos, scoreboard e comportamento dos espectadores.
- `messages.yml` — mensagens do plugin, com suporte aos códigos de cor tradicionais (`&`).
- `arenas.yml` — mundos e posições de spawn, chegada, boneca e lobby de cada arena.

As arenas devem ser configuradas com os comandos administrativos de posição antes de receber jogadores. Os intervalos de duração dos sinais e o raio ou região da chegada também fazem parte das opções previstas.

---

## 📦 Instalação

Quando a implementação e o artefato estiverem disponíveis:

1. Compile o projeto com o wrapper Gradle, usando `gradlew build` no Windows ou `./gradlew build` em Linux/macOS.
2. Copie o JAR gerado em `build/libs/` para a pasta `plugins/` do servidor Spigot 1.8.9.
3. Inicie ou reinicie o servidor para gerar e carregar os arquivos de configuração.
4. Configure as arenas e seus pontos com os comandos administrativos.

> O repositório ainda não contém os arquivos de build ou o JAR. As etapas acima descrevem o fluxo de instalação previsto e dependem da implementação do projeto.

---

## 🧩 Tecnologia

- **Linguagem:** Java
- **Servidor:** Spigot 1.8.9
- **NMS:** `v1_8_R3`
- **Build:** Gradle Kotlin DSL
- **Autor definido na especificação:** joaoooomartins

---

## 🚦 RedLightGreenLight

> GREEN LIGHT: avance até a chegada.  
> RED LIGHT: pare antes que a boneca veja você.
