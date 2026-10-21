# Validação do pacote 1.0

O patch foi gerado comparando a ISO americana original com a ISO traduzida 1.0.

| Arquivo | SHA-256 |
| --- | --- |
| ISO original | `1c7a1ee34b56612593625ad327f38e3b955c850320b13cfaecada326f86df85e` |
| Patch `.xdelta` | `44682a6b84eef5a62d5073fac30d5577075f9591097400fe3321f406ca39ab8a` |
| ISO recriada pelo aplicador | `6bfa57c7e29bb3a7ee613e7102606a947f12ea5f39500d55f44049a01c8744a9` |

Testes realizados:

- Aplicação completa usando o `APLICAR_PATCH.ps1` deste pacote no Windows PowerShell.
- Conferência do tamanho e SHA-256 da origem antes de aplicar.
- Conferência do patch e do executável xdelta contra o manifesto.
- Conferência do tamanho e SHA-256 da ISO gerada antes de criar a saída definitiva.
- Confirmação de que a saída é idêntica à ISO traduzida 1.0 de referência.
- Rejeição de uma ISO já traduzida usada como origem, sem gerar uma nova ISO.
- Recusa de um caminho de saída já existente, sem sobrescrever o arquivo.
- Conferência da integridade e dos arquivos incluídos no ZIP.

O patch tem **906.541 bytes**. Ele não contém uma ISO completa.
O comando de geração, usando xdelta 3.2.2, foi:

```text
xdelta3 -e -9 -a -G -A -D -R -s "Warriors Orochi (USA).iso" "Warriors Orochi (USA) (PT-BR - Versao 1.0).iso" "Warriors_Orochi_USA_PTBR_v1.0.xdelta"
```

Esses testes comprovam a reconstrução do arquivo. Eles não substituem o teste
de todas as fases, textos e menus no jogo. As limitações da tradução estão no README.
