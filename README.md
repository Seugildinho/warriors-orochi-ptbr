# Warriors Orochi — Tradução PT-BR 1.0 (PS2)

**[Baixar o pacote completo PT-BR 1.0](https://github.com/Seugildinho/warriors-orochi-ptbr/releases/download/v1.0/Warriors_Orochi_PTBR_v1.0.zip)**

[Página da Release e arquivos de download](https://github.com/Seugildinho/warriors-orochi-ptbr/releases/tag/v1.0)

Baixe o ZIP da Release e extraia tudo para aplicar a tradução. O botão
**Code → Download ZIP** baixa apenas a documentação deste repositório.
Os caminhos dos aplicadores, do patch e da pasta `ferramentas` citados abaixo
se referem ao conteúdo do pacote completo da Release.

SHA-256 do pacote ZIP: `618ef628a5e5142168e341c23bb1c7ca27797fdab7f7cc6589fe25b37055df83`.

Patch de tradução em português brasileiro para **Warriors Orochi (USA)** de PlayStation 2.
O pacote contém o patch, um aplicador para Windows e instruções. A ISO do jogo não acompanha o projeto.

## Qual versão do jogo usar

Use uma cópia da sua **ISO americana original, sem modificações**:

| Identificação | Valor obrigatório |
| --- | --- |
| Jogo | Warriors Orochi |
| Plataforma | PlayStation 2 |
| Região | USA / NTSC-U |
| Código | **SLUS-21662** (executável `SLUS_216.62`) |
| Tamanho original | **2.677.604.352 bytes** |
| SHA-256 original | `1c7a1ee34b56612593625ad327f38e3b955c850320b13cfaecada326f86df85e` |

**O SHA-256 é a identificação decisiva.** O nome do arquivo pode ser diferente.
Não aplique sobre uma das Betas, sobre a ISO já traduzida, sobre outra região,
Warriors Orochi 2 ou uma imagem reconstruída com hash diferente.
Se tiver CHD, CSO ou um arquivo compactado, primeiro obtenha a ISO original correspondente;
a ISO resultante precisa ter o tamanho e o SHA-256 acima.

## Como aplicar no Windows

1. Baixe o pacote completo da versão **1.0** e use **Extrair tudo** no ZIP.
2. Deixe a pasta em um local com permissão de escrita e pelo menos **3 GB livres**, além do espaço da ISO original.
3. Abra **`APLICAR_PATCH.cmd`** e selecione sua ISO original. Também pode arrastar a ISO sobre esse arquivo.
4. Aguarde a verificação da origem, a aplicação e a verificação final. Não feche a janela durante o processo.
5. Quando aparecer **CONCLUÍDO**, abra a nova ISO no PCSX2 ou no carregador que você já usa.

Saída criada na pasta do patch:

```text
Warriors Orochi (USA) (PT-BR - Versao 1.0).iso
```

A origem permanece intacta. O aplicador recusa uma ISO incompatível e não sobrescreve
arquivos existentes. Não é necessário instalar Python, usar administrador ou instalar o xdelta:
o executável oficial **xdelta 3.2.2 para Windows x64** está incluído.
Em outro sistema ou arquitetura, use a ferramenta correspondente pelo método manual abaixo.

### PowerShell com caminhos personalizados

Na pasta extraída:

```powershell
powershell.exe -NoProfile -ExecutionPolicy Bypass -File .\APLICAR_PATCH.ps1 -IsoOriginal "D:\Jogos\Warriors Orochi (USA).iso" -IsoSaida "D:\Jogos\Warriors Orochi PTBR 1.0.iso"
```

## Aplicação manual com xdelta

Use o xdelta oficial. A versão **3.2.2** é a usada e testada neste pacote:
[downloads oficiais](https://github.com/jmacd/xdelta/releases/tag/v3.2.2).
No Windows, execute na pasta extraída:

```powershell
.\ferramentas\xdelta3.exe -d -D -R -s "Warriors Orochi (USA).iso" "Warriors_Orochi_USA_PTBR_v1.0.xdelta" "Warriors Orochi PTBR 1.0.iso"
```

No Linux/macOS, usando o executável adequado:

```sh
xdelta3 -d -D -R -s "Warriors Orochi (USA).iso" "Warriors_Orochi_USA_PTBR_v1.0.xdelta" "Warriors Orochi PTBR 1.0.iso"
```

No método manual, confira os hashes da origem e da saída por sua conta.
Para conferir no Windows:

```powershell
Get-FileHash -LiteralPath "Warriors Orochi (USA).iso" -Algorithm SHA256
Get-FileHash -LiteralPath "Warriors Orochi PTBR 1.0.iso" -Algorithm SHA256
```

## Resultado esperado

| Verificação | ISO traduzida 1.0 |
| --- | --- |
| Tamanho | **2.677.612.544 bytes** |
| SHA-256 | `6bfa57c7e29bb3a7ee613e7102606a947f12ea5f39500d55f44049a01c8744a9` |

Com esse hash, a aplicação recriou exatamente a versão 1.0.
Os hashes do patch e da ferramenta estão em `manifesto.json` e `SHA256SUMS.txt`.

## Conteúdo e estado da tradução

- Diálogos, legendas de cenas e textos de batalha em português.
- Nomes de armas, habilidades, efeitos, requisitos e diversos menus traduzidos.
- Termos como Abate, Clarão, Dreno, Clones e Rapidez padronizados.
- Fontes anteriores à Beta 0.6 restauradas, com ajustes de margens e encaixe.
- 24.251 ocorrências de texto alteradas e 443 rótulos de imagens traduzidos.

As vozes continuam em inglês. Os textos que usam a fonte original do jogo são
inseridos sem acentos; rótulos traduzidos em imagens podem ter acentos.
Ainda pode haver texto em inglês, traduções literais e ajustes de contexto ou espaço a revisar.
A numeração **1.0** identifica esta entrega; a revisão integral de todos os diálogos
e fases ainda não foi concluída. Esta edição não recebeu um novo teste completo no emulador
nem foi validada em um PS2 físico. Isso é separado do teste de integridade do patch.

## Problemas comuns

- **ISO incompatível / SHA-256 diferente:** confira região, código, tamanho e hash.
  Renomear o arquivo não muda sua versão. Não force a aplicação.
- **Arquivo de saída já existe:** escolha outro nome pelo PowerShell ou mova sua cópia anterior.
- **Patch ou ferramenta corrompido:** baixe e extraia novamente o pacote completo.
- **Sem espaço / acesso negado:** use uma pasta gravável com pelo menos 3 GB livres.
- **Texto errado ou cortado no jogo:** abra uma issue com captura, personagem,
  fase e caminho do menu. Informe que está usando a versão 1.0.

## Ferramenta incluída

Xdelta 3.2.2, Copyright Joshua MacDonald, sem alterações no executável.
Projeto e fontes: [jmacd/xdelta](https://github.com/jmacd/xdelta/tree/v3.2.2).
Licença Apache 2.0 em `ferramentas/LICENSE-xdelta.txt`.
Detalhes de procedência em `ferramentas/ORIGEM.md`.

Este é um projeto de tradução de fã. O pacote não inclui o jogo, BIOS ou saves.
O jogo e seus elementos pertencem aos respectivos titulares.
