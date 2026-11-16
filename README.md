# Painel do Paciente — Apresentação e Prova de Conceito (nome provisório)

Aplicação web estática e autocontida de demonstração (**terceira iteração**) desenvolvida para o pitch do **Grupo 3** da formação **Médicos Híbridos**.

O arquivo único reúne duas frentes na mesma página, sem servidor, sem frameworks externos e com operação completa offline:

1. **Apresentação do projeto (10 seções):** narrativa estruturada em bandas visuais alternadas e menu fixo de âncoras cobrindo abertura executiva, fragmentação da jornada pré-procedimento com evidência científica mapeada, público-alvo inicial (marcado como hipótese), proposta do painel único com analogia ao painel de voos do aeroporto, arquitetura de integração em duas rotas (HL7 FHIR simulado e questionário do paciente), escopo fora da primeira versão (incluindo fronteira regulatória Anvisa RDC 657/2022 e LGPD), hipótese de modelo de negócio B2B com dimensionamento de mercado TAM, SAM e SOM (referência CNES e simulador interativo), plano de crescimento em 3 horizontes e 3 pivôs estratégicos, medida de tração, seis pilares arquiteturais, matriz de riscos, próximos passos externos de validação e composição do time (**Augusto Linhares**, **Marcelo Teles** e **Karina**).
2. **Demonstração conceitual (PoC):** protótipo navegável que comprova a leitura imediata do estado do paciente em uma única tela, com acionamento por perfil profissional e registro em memória para cada etapa.

---

## Arquivos desta pasta

| Arquivo | Descrição |
|---|---|
| `index.html` | Aplicação web completa (HTML, CSS e JavaScript puro no mesmo arquivo autocontido). |
| `README.md` | Guia de abertura, edição dos dados fictícios e resumo da estrutura. |
| `roteiro-demo.md` | Roteiro cronometrado de 90 segundos para conduzir a demonstração ao vivo. |
| `relatorio-agentes.md` | Registro das etapas executadas, auditorias técnicas e correções aplicadas. |

---

## Como abrir

1. Abra o arquivo `index.html` diretamente no navegador (duplo clique no arquivo local).
2. Não é necessária conexão com a internet, compilação ou servidor local: todas as regras visuais, ícones vetoriais e dados fictícios estão incorporados no próprio arquivo com fontes padrão do sistema operacional.
3. A demonstração também é publicada na internet via GitHub Pages (acessível em navegador moderno sem instalação).

---

## Como editar os dados fictícios sem programar

Todo o bloco editável fica isolado no topo do `<script>`, na seção **`1. CONFIGURAÇÕES EDITÁVEIS (ALTERE AQUI SEM PRECISAR PROGRAMAR)`**, dentro de `poc-painel/index.html`.

Principais constantes disponíveis para ajuste rápido:

- **`NOME_PRODUTO`** e **`SELO_NOME_PRODUTO`**: alteram de forma centralizada o título provisório (`"Painel do Paciente"`) e o selo (`"nome provisório"`) em toda a interface, inclusive no diagrama da apresentação e no título da aba do navegador.
- **`DATA_SIMULADA_HOJE`**: data de referência exibida nos quadros, nas etapas avançadas em memória e no conjunto HL7 FHIR simulado (`"15/11"`).
- **`ETAPAS_JORNADA`**: os 8 marcos fixos da jornada (`"Agendado"` até `"Pós-procedimento"`).
- **`FONTES`**: rótulos das fontes de origem dos dados (`"Sistema da clínica (FHIR simulado)"`, `"Questionário do paciente"`, `"Recepção (confirmação)"`, `"Avaliação de enfermagem"`, `"Avaliação pré-anestésica"` e `"Médico executor"`).
- **`ORIENTACOES_ILUSTRATIVAS`**: listas de exemplo para pré-procedimento e pós-procedimento, exibidas sempre com o selo `"Conteúdo ilustrativo — a validar pela equipe clínica"`.
- **`PACIENTES_INICIAIS`**: vetor com os 5 pacientes fictícios, seus dados simulados do sistema e respostas de questionário, utilizando os profissionais fictícios com título completo (`Beatriz Moura — Médica anestesiologista`, `Marcos Oliveira — Enfermeiro`, `Henrique Azevedo — Médico executor`).

---

## Recursos da demonstração interativa

- **Apresentação — Simulador de mercado e estratégia (Seção 7):** âncora de retorno por redução de suspensões evitáveis, cartões TAM (1,56 bilhão por ano), SAM (504 milhões por ano) e SOM (R$ 33,0 milhões por ano considerando 5% das clínicas do SAM com módulo expandido), simulador bottom-up interativo (`#simulador-tam-sam-som`) com seletores de clínicas e assinatura mensal, 3 horizontes de crescimento e 3 pivôs estratégicos — todos rotulados como hipótese.
- **A. Quadro da Clínica:** visão geral com 5 pacientes fictícios, cartões de resumo por status (`Pronto`, `Pendente`, `Atenção`), barra de progresso (`Etapa X de 8`), coluna `Acionamento atual` com o perfil profissional exigido no estágio e instrução direta, filtro por perfil acionado, botão `Atender` e alternador de cenário (`Clínica com sistema (FHIR simulado)` contra `Clínica sem sistema (só questionário)`).
- **B. Detalhe do Paciente:** painel executivo desenhado para leitura integral sem rolagem vertical na resolução `1366×768`, combinando cabeçalho de status, linha do tempo de 8 etapas, cartão de dados críticos com origem por campo, índice de massa corporal calculado em português do Brasil, alertas estritamente informativos (divergências e campos pendentes), bloco **`Painel do perfil: [Perfil]`** com status **`ACIONADO AGORA`** ou **`Aguardando`**, botão **`Registrar / Editar ([Perfil])`** abrindo o modal de registro em memória para cada um dos quatro perfis clínicos e visualizador `Ver dado bruto (FHIR)`.
- **C. Visão do Paciente (Celular):** interface responsiva com orientações ilustrativas (abas de pré-procedimento e pós-procedimento liberadas após conclusão pelo médico executor) e questionário pré-procedimento simplificado para leigos com linguagem cotidiana, botões amplos de `Sim` e `Não` e chips de toque único para respostas rápidas.
- **Perfis com ação real:** alternância entre `Recepção`, `Enfermagem`, `Anestesista`, `Médico executor` e `Paciente`, destacando campos críticos e habilitando registro, aferição presencial, conciliação de divergências e liberação de pós-procedimento diretamente na memória da sessão.
- **Tour guiado e reinício:** percurso de 8 passos sincronizado com cenários e modais, além do botão `Reiniciar demonstração` para restaurar imediatamente o estado inicial em memória sem usar `localStorage`.

---

## Governança e avisos obrigatórios

- **Somente dados fictícios:** todos os nomes de pacientes, datas de nascimento, procedimentos e profissionais assistenciais são fictícios, sinalizados pelo aviso fixo `"Demonstração com dados fictícios"`.
- **Nenhuma conduta clínica:** alertas, conciliações e contadores verificam ou registram exclusivamente fatos informativos informados pelos profissionais ou pelo paciente, nunca recomendando suspensão, prescrição, liberação ou escore de risco clínico (fidelidade à fronteira da Anvisa RDC 657/2022).
- **Conteúdo clínico ilustrativo:** dados críticos e orientações carregam o selo `"Conteúdo ilustrativo — a validar pela equipe clínica"`.
- **Sem nomes de empregadores, concorrentes ou marcas reais:** não há menções a empresas empregadoras de integrantes, sistemas concorrentes nem logotipos de terceiros.
