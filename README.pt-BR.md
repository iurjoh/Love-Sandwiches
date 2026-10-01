# Love Sandwiches automation

[English](README.md)

## Ideia e processo

Exercício Python de curso para seis valores de vendas, excedente e próximo estoque por Google Sheets. Código revisado em 01/10/2026. Sequência de funções registra o fluxo; não foi encontrado plano pessoal datado ou diário de design.

## Arquitetura e design

`run.py` autoriza conta de serviço de creds.json local e abre planilha love_sandwiches. Recebe seis inteiros separados por vírgula, adiciona vendas, calcula excedente pelo último estoque, adiciona excedente, faz média das últimas cinco vendas por coluna, acrescenta 10%, arredonda e adiciona estoque. Interface de terminal; pacote Node acompanha wrapper de terminal do Code Institute.

## Cuidados de configuração

Não execute ou importe run.py só para inspecionar: autorização acontece no carregamento e main() roda imediatamente. Escreve em sales, surplus e stock. Esta atualização não consultou credenciais, conectou Sheets, leu registros ou executou programa.

Use somente planilha descartável autorizada separadamente e valores fictícios em testes futuros. requirements.txt fixa gspread 5.6.0 e pacotes históricos Google auth. Script pede scopes spreadsheets, drive.file e Drive amplo; revise acesso mínimo antes de configurar credencial. Segredos persistentes fora de código/capturas. Deploy atual não confirmado.

## Testes e limites

Suíte não encontrada na raiz revisada. Validador exige seis inteiros, mas aceita negativos. Cálculo presume linhas numéricas, colunas consistentes e histórico não vazio. Teste entradas inválidas, planilhas ausentes, histórico curto/vazio, cabeçalhos, arredondamento e falhas API com mocks ou planilha descartável. Appends separados podem duplicar linhas em retry após falha parcial. Refatore efeitos de importação antes de testes isolados. Nenhum resultado afirmado.

## Capturas

Nenhuma captura verificada/adicionada. Capturas futuras de terminal em `docs/assets/` devem usar números fictícios e esconder credenciais, identificadores e dados de negócio. Registre comandos/resultados reais, sem inventar updates bem-sucedidos.

## Créditos e licença

Direitos de curso/template/dependências mantidos. Manifest existente declara ISC; nenhuma licença nova adicionada ou aplicada a terceiros. README original preservado no [apêndice em inglês](README.md#original-readme).
