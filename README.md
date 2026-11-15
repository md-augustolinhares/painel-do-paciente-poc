# Painel do Paciente — Apresentação e Prova de Conceito (nome provisório)

Aplicação web estática e autocontida de demonstração (**segunda versão**) desenvolvida para o pitch do **Grupo 3** da formação **Médicos Híbridos**.

O arquivo único reúne duas frentes na mesma página, sem servidor, sem frameworks externos e com operação completa offline:

1. **Apresentação do projeto (10 seções):** narrativa estruturada em bandas visuais alternadas e menu fixo de âncoras cobrindo abertura executiva, fragmentação da jornada pré-procedimento, público-alvo inicial (marcado como hipótese), proposta do painel único com analogia ao painel de voos do aeroporto, arquitetura de integração em duas rotas (HL7 FHIR simulado e questionário do paciente), escopo fora da primeira versão (incluindo fronteira regulatória Anvisa RDC 657/2022 e LGPD), hipótese de modelo de negócio B2B sem preço fixado, histórico com os 6 pontos de mentoria e matriz de riscos, próximos passos de validação e composição do time (**Augusto Linhares**, **Marcelo Teles** e **Karina**).
2. **Demonstração conceitual (PoC):** protótipo navegável que comprova a leitura imediata do estado do paciente em uma única tela, mantendo o estado apenas em memória.

---

## Arquivos desta pasta

| Arquivo | Descrição |
|---|---|
| `index.html` | Aplicação web completa (HTML, CSS e JavaScript puro no mesmo arquivo, com 4.866 linhas e 183.925 bytes). |
| `README.md` | Guia de abertura, edição dos dados fictícios e resumo da estrutura. |
| `roteiro-demo.md` | Roteiro cronometrado de 90 segundos para conduzir a demonstração ao vivo. |
| `relatorio-agentes.md` | Registro das etapas executadas, auditorias técnicas e correções aplicadas. |

---

## Como abrir

1. Abra o arquivo `index.html` diretamente no navegador (duplo clique no arquivo local).
2. Não é necessária conexão com a internet, compilação ou servidor local: todas as regras visuais, ícones vetoriais e dados fictícios estão incorporados no próprio arquivo com fontes padrão do sistema operacional.
3. A demonstração também é publicada via GitHub Pages a partir do repositório espelho `D:\Repositorios\painel-do-paciente-poc`.

---

## Como editar os dados fictícios sem programar

Todo o bloco editável fica isolado no topo do `<script>`, na seção **`1. CONFIGURAÇÕES EDITÁVEIS (ALTERE AQUI SEM PRECISAR PROGRAMAR)`**, a partir da **linha 3071** de `index.html`.

Principais constantes disponíveis para ajuste rápido:

- **`NOME_PRODUTO`** e **`SELO_NOME_PRODUTO`**: alteram de forma centralizada o título provisório (`"Painel do Paciente"`) e o selo (`"nome provisório"`) em toda a interface, inclusive no diagrama da apresentação e no título da aba do navegador.
- **`DATA_SIMULADA_HOJE`**: data de referência exibida nos quadros, nas etapas avançadas em memória e no conjunto HL7 FHIR simulado (`"15/11"`).
- **`ETAPAS_JORNADA`**: os 8 marcos fixos da jornada (`"Agendado"` até `"Pós-procedimento"`).
- **`FONTES`**: rótulos das três fontes de origem dos dados (`"Sistema da clínica (FHIR simulado)"`, `"Questionário do paciente"` e `"Avaliação de enfermagem"`).
- **`ORIENTACOES_ILUSTRATIVAS`**: listas de exemplo para pré-procedimento e pós-procedimento, exibidas sempre com o selo `"Conteúdo ilustrativo — a validar pela equipe clínica"`.
- **`PACIENTES_INICIAIS`**: vetor com os 5 pacientes fictícios, seus dados simulados do sistema e respostas de questionário, utilizando os profissionais fictícios com título completo (`Beatriz Moura — Médica anestesiologista`, `Marcos Oliveira — Enfermeiro`, `Henrique Azevedo — Médico executor`).

---

## Recursos da demonstração interativa

- **A. Quadro da Clínica:** visão geral com 5 pacientes fictícios, cartões de resumo por status (`Pronto`, `Pendente`, `Atenção`), barra de progresso (`Etapa X de 8`), selos de `Fontes ativas`, busca por nome, filtros por prontidão, alternador de cenário (`Clínica com sistema (FHIR simulado)` contra `Clínica sem sistema (só questionário)`) e faixa de atalhos rápidos (`Marina Ferreira Costa`, `Carlos Eduardo Mendes` e `Roberto Almeida Nascimento`).
- **B. Detalhe do Paciente:** painel executivo desenhado para leitura integral sem rolagem vertical na resolução `1366×768`, combinando cabeçalho de status, linha do tempo de 8 etapas, cartão de dados críticos com origem por campo, índice de massa corporal calculado em português do Brasil, alertas estritamente informativos (divergências e campos pendentes), botão `Avançar etapa` e visualizador `Ver dado bruto (FHIR)`.
- **C. Visão do Paciente (Celular):** interface responsiva com orientações ilustrativas (abas de pré-procedimento e pós-procedimento) e questionário pré-procedimento interativo de 7 perguntas que atualiza pendências e divergências em tempo real na memória.
- **Cinco perfis de leitura:** seletor entre `Recepção`, `Enfermagem`, `Anestesista`, `Médico executor` e `Paciente`, destacando automaticamente os campos prioritários de cada papel sem ocultar informações críticas.
- **Tour guiado e reinício:** percurso de 8 passos sincronizado com cenários e modais, além do botão `Reiniciar demonstração` para restaurar imediatamente o estado inicial em memória sem usar `localStorage`.

---

## Governança e avisos obrigatórios

- **Somente dados fictícios:** todos os nomes de pacientes, datas de nascimento, procedimentos e profissionais assistenciais são fictícios, sinalizados pelo aviso fixo `"Demonstração com dados fictícios"`.
- **Nenhuma conduta clínica:** alertas e contadores verificam exclusivamente presença ou divergência factual de informação, nunca recomendando suspensão, liberação ou escore de risco clínico (fidelidade à fronteira da Anvisa RDC 657/2022).
- **Conteúdo clínico ilustrativo:** dados críticos e orientações carregam o selo `"Conteúdo ilustrativo — a validar pela equipe clínica"`.
- **Sem nomes de empregadores, concorrentes ou marcas reais:** não há menções a empresas empregadoras de integrantes, sistemas concorrentes nem logotipos de terceiros.
