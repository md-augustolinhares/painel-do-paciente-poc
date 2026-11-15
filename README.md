# Painel do Paciente *(nome provisório)* — Apresentação e Prova de Conceito (PoC)

Aplicação web estática e autocontida do **Grupo 3** (formação **Médicos Híbridos**), reunindo em um único arquivo HTML a apresentação de apoio ao pitch e uma prova de conceito (PoC) navegável de painel pré-procedimento para clínicas de pequeno e médio porte.

> **Aviso obrigatório:** Demonstração com **dados 100% fictícios**. Nenhum dado real de paciente, empresa empregadora, hospital ou marca comercial é utilizado. Todo conteúdo clínico exibido é ilustrativo e deve ser validado pela equipe clínica.

---

## Como acessar

### 1. Online (GitHub Pages)
- **Demonstração publicada:** `https://md-augustolinhares.github.io/painel-do-paciente-poc/`
- **Repositório público:** `https://github.com/md-augustolinhares/painel-do-paciente-poc`

### 2. Offline (duplo clique)
1. Baixe ou clone este diretório.
2. Abra o arquivo `index.html` com um duplo clique em qualquer navegador moderno (Chrome, Edge, Firefox ou Safari).
3. Não exige internet, servidor, build, Node.js, CDN ou instalação de dependências.
4. Todo o estado da demonstração fica apenas em memória (sem `localStorage` ou cookies). Clique em **Reiniciar demonstração** a qualquer momento para voltar ao estado inicial.

---

## O que existe neste diretório

| Arquivo | Função |
|---|---|
| `index.html` | Aplicação completa (HTML5, CSS3 e JavaScript puro) com **Parte 1: Apresentação do Projeto (10 seções)** e **Parte 2: Demonstração Conceitual (Telas A, B e C, regras determinísticas, JSON FHIR simulado e Tour Guiado)**. |
| `README.md` | Este guia de uso, edição dos dados e regras de governança. |
| `roteiro-demo.md` | Roteiro cronometrado de 90 segundos (8 passos) para apresentar a demonstração ao vivo. |
| `relatorio-agentes.md` | Registro da execução, revisões de qualidade e segurança e análise de lacunas da construção com os agentes do acervo. |

---

## Como editar o nome do produto e os dados fictícios (sem saber programar)

1. Faça uma cópia de segurança do arquivo `index.html`.
2. Abra `index.html` em um editor de texto simples (Bloco de Notas, VS Code ou Notepad++).
3. Procure por **`1. CONFIGURAÇÕES EDITÁVEIS`** dentro da tag `<script>` (por volta da linha 2105):
   - **Mudar o nome do produto:** altere o texto entre aspas na linha:
     ```javascript
     const NOME_PRODUTO = "Painel do Paciente";
     const SELO_NOME_PRODUTO = "nome provisório";
     ```
   - **Mudar orientações ilustrativas:** edite os textos dentro de `ORIENTACOES_ILUSTRATIVAS` (`pre` e `pos`).
   - **Mudar pacientes, procedimentos ou dados clínicos fictícios:** edite o bloco `PACIENTES_INICIAIS` (5 pacientes: `p1` a `p5`). Cada paciente possui:
     - `nome`, `idade`, `dataNascimento`, `procedimento`, `dataHora`, `responsavel`;
     - `etapaAtual`: número de `0` a `7` correspondente às 8 posições de `ETAPAS_JORNADA` (`0 = Agendado` até `7 = Pós-procedimento`);
     - `datasEtapas`: lista de datas curtas exibidas nas etapas concluídas;
     - `sistema`, `questionario` e `enfermagem`: dados por fonte (`null` indica que aquela fonte ainda não enviou respostas);
     - `usaAnticoagulante`: `true` ou `false`.
4. Salve o arquivo e recarregue `index.html` no navegador.
5. **Atenção:** mantenha todas as aspas (`"..."`) e vírgulas exatamente nos mesmos lugares ao editar.

---

## O que é fictício e limites desta PoC

- **Dados fictícios:** todos os nomes de pacientes, datas, idades, procedimentos, alergias, medicações, comorbidades e identificadores no JSON HL7 FHIR são sintéticos e ilustrativos.
- **Regras ilustrativas (sem IA e sem conduta clínica):** a classificação em **Pronto**, **Pendente** ou **Atenção** usa regras determinísticas simples. O painel exibe apenas alertas informativos (completude e divergência entre fontes) e **nunca** sugere conduta médica ou decisão clínica.
- **Conteúdo a validar:** os dados críticos e as orientações pré e pós-procedimento são provisórios e carregam a marca **Conteúdo ilustrativo — a validar pela equipe clínica**.
- **Fora do escopo desta v1:** integração real com prontuários eletrônicos em produção, leitura de texto livre com IA, controle real de acesso/autenticação e módulo financeiro/cobrança.
