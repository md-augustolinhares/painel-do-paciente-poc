# Roteiro da Demonstração ao Vivo (90 segundos)

**Objetivo do pitch:** provar em uma tela que a equipe clínica e administrativa entende o estado de prontidão do paciente sem digitar nada a mais e sem trocar o prontuário existente.

**Preparação antes de falar:**
1. Abra `index.html` no navegador em resolução de notebook (`1366×768` ou maior) ou utilize a versão publicada no GitHub Pages.
2. Mantenha o botão **Reiniciar demonstração** pronto caso precise repetir o fluxo com os dados iniciais restaurados.

---

## 0 a 15 segundos — Abertura e analogia do aeroporto
- **Na tela:** aba **Apresentação do Projeto** (Seção 1 `Abertura` e Seção 4 `A solução`).
- **O que falar:**
  > "Na jornada pré-procedimento com sedação, cada profissional anota no seu sistema isolado e o paciente acaba repetindo os mesmos dados. Nosso conceito — com nome provisório Painel do Paciente — funciona como o painel de voos do aeroporto: cada companhia continua com o seu sistema, e o painel não substitui nenhum deles; ele só reúne voo, portão e status para toda a clínica enxergar na mesma página."
- **Ação:** clique em **Ver a demonstração**.

---

## 15 a 35 segundos — Quadro da clínica (A. Quadro da Clínica)
- **Na tela:** sub-aba **A. Quadro da Clínica** no cenário **Clínica com sistema (FHIR simulado)**.
- **O que falar:**
  > "Esta é a tela inicial da clínica. Temos 5 pacientes fictícios com barras de progresso de etapa, fontes ativas e três status em cor e texto: Pronto, Pendente e Atenção. Em segundos, quem coordena o dia sabe onde cada paciente está e o que precisa de conferência antes da sedação."
- **Ação:** clique no atalho rápido **Marina Ferreira Costa (Atenção)** na barra superior ou clique diretamente no nome da paciente na tabela.

---

## 35 a 55 segundos — Leitura sem rolagem e detecção de divergência (B. Detalhe do Paciente)
- **Na tela:** **B. Detalhe do Paciente** (tudo visível sem rolar em `1366×768`).
- **O que falar:**
  > "No detalhe da Marina, toda a linha do tempo e os dados críticos aparecem juntos na mesma tela. Observe o alerta de Atenção: o questionário aponta Alergia a látex (edema e urticária), enquanto o sistema da clínica registra Sem alergias registradas. O painel não dá conduta clínica nem manda suspender nada — ele apenas sinaliza o dado divergente para decisão humana. Se trocarmos o perfil para Anestesista, o painel destaca automaticamente alergias, medicações em uso e confirmação de jejum."
- **Ação:** alterne o seletor **Perfil** para **Anestesista** (mostrando a atribuição a `Beatriz Moura — Médica anestesiologista`) e clique em **Ver dado bruto (FHIR)** por alguns segundos, fechando o modal em seguida.

---

## 55 a 75 segundos — Clínica sem sistema e visão do paciente (C. Visão do Paciente (Celular))
- **Na tela:** alterne o **Cenário** para **Clínica sem sistema (só questionário)** e selecione o atalho **Carlos Eduardo Mendes (Pendente)**, acessando **C. Visão do Paciente (Celular)** (ou escolhendo o perfil **Paciente**).
- **O que falar:**
  > "Se a clínica não tiver sistema integrado por padrão HL7 FHIR simulado, entramos pela segunda rota: o próprio paciente preenche o questionário pré-procedimento no celular e lê orientações ilustrativas para validar com a equipe clínica. Ao enviar as respostas, o painel recalcula pendências, índice de massa corporal e alertas de anticoagulante na hora, sem a equipe digitar uma linha a mais."
- **Ação:** clique em **Preencher com dados de exemplo**, marque o uso de anticoagulante (ou altere o peso), clique em **Enviar questionário e atualizar painel** e clique em **Ver Detalhe do Paciente**.

---

## 75 a 90 segundos — Governança e encerramento
- **Na tela:** detalhe atualizado em memória e botões **Iniciar tour** / **Reiniciar demonstração**.
- **O que falar:**
  > "Toda a demonstração usa dados fictícios, não armazena dados fora da memória do navegador e não emite recomendação clínica — mantendo nosso recorte informativo alinhado às cautelas regulatórias da RDC 657/2022 da Anvisa e da LGPD. Como próximos passos, vamos validar estes dados críticos com a anestesiologia do time — Karina, Marcelo Teles e Augusto Linhares — e testar o protótipo com 3 clínicas e 3 a 5 pessoas. Obrigado."
- **Ação opcional para perguntas:** caso a banca queira explorar passo a passo após a apresentação, acione **Iniciar tour** para percorrer automaticamente os 8 cenários-chave.
