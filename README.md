# Contalger — Complementador E113

Aplicação web estática para complementar o **Registro E113 da EFD ICMS/IPI** a partir da apuração já calculada e do arquivo EFD gerado pelo ERP.

## O que o app faz

- Importa a apuração de **NF-e** em Excel.
- Importa opcionalmente a apuração de **CT-e FOB** em Excel.
- Importa o arquivo **EFD ICMS/IPI (.txt)** já preenchido.
- Faz o cruzamento dos dados e prepara E113 por produto para os ajustes:
  - `PI050039` — débito especial 6,3%.
  - `PI050040` — débito especial 3,0%.
  - `PI050049` — antecipação parcial.
  - `PI030010` — estorno de débito em saídas interestaduais.
- Pode criar registros `0200` ausentes a partir da apuração.
- Recalcula os totalizadores necessários do arquivo EFD.
- Gera um novo TXT, preservando o arquivo original.
- Exporta CSV de conferência.

## Privacidade

O processamento dos arquivos é realizado **no navegador do usuário**. A aplicação não possui backend próprio e não envia as planilhas ou o EFD para um servidor da Contalger.

> **Importante:** não publique no repositório arquivos reais de clientes, EFDs, planilhas fiscais, certificados digitais ou qualquer dado confidencial. O repositório deve conter somente os arquivos da aplicação.

## Publicar no GitHub Pages

1. Crie um repositório no GitHub, por exemplo `complementador-e113`.
2. Envie para a raiz do repositório os arquivos deste pacote, mantendo `index.html` na raiz.
3. No GitHub, abra **Settings → Pages**.
4. Em **Build and deployment**, escolha **Deploy from a branch**.
5. Selecione a branch `main` e a pasta `/ (root)`.
6. Salve e aguarde a publicação.

Não é necessário Node.js, Python, banco de dados ou servidor próprio.

## Dependência

A leitura das planilhas utiliza **SheetJS/xlsx 0.18.5**, carregado por CDN. Por isso, a máquina precisa ter acesso à internet ao abrir a aplicação publicada.

## Uso

1. Selecione a apuração de NF-e.
2. Se houver, selecione a apuração de CT-e FOB.
3. Selecione o TXT da EFD ICMS/IPI.
4. Clique em **Processar e cruzar**.
5. Confira os valores e vínculos.
6. Gere o novo arquivo EFD.
7. **Valide o TXT no PVA antes de transmitir.**

## Observação

Esta é uma ferramenta de apoio à escrituração. A validação fiscal e a conferência final dos registros permanecem indispensáveis antes da transmissão da EFD.
