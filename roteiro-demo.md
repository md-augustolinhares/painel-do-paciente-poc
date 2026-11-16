# Roteiro da Demonstração ao Vivo (90 segundos)

**Objetivo do pitch:** provar em uma tela que a equipe clínica e administrativa entende o estado de prontidão do paciente sem digitar nada a mais e sem trocar o prontuário existente.

**Preparação antes de falar:**
1. Abra `index.html` no navegador em resolução de notebook (`1366×768` ou maior) ou utilize a versão publicada no GitHub Pages.
2. Mantenha o botão **Reiniciar demonstração** pronto caso precise repetir o fluxo com os dados iniciais restaurados.

---

## 0 a 15 segundos — Abertura, analogia do aeroporto e mercado
- **Na tela:** aba **Apresentação do Projeto** (Seção 1 `Abertura`, Seção 4 `A solução` e Seção 7 `Modelo de negócio, mercado e crescimento`).
- **O que falar:**
  > "Na jornada pré-procedimento com sedação, cada profissional anota no seu sistema isolado e o paciente acaba repetindo os mesmos dados. Nosso conceito — com nome provisório Painel do Paciente — funciona como o painel de voos do aeroporto: cada companhia continua com o seu sistema, e o painel reúne voo, portão e status para toda a equipe enxergar na mesma tela. No Brasil, são cerca de 108,5 mil estabelecimentos ambulatoriais especializados no CNES e 25 mil clínicas privadas de procedimentos no nosso mercado endereçável, mirando 1.250 clínicas (5%) em nossa hipótese de escala."
- **Ação:** mostre o cartão do TAM, SAM e SOM na Seção 7 e clique em **Ver a demonstração**.

---

## 15 a 35 segundos — Quadro da clínica com acionamento por perfil (A. Quadro da Clínica)
- **Na tela:** sub-aba **A. Quadro da Clínica** no cenário **Clínica com sistema (FHIR simulado)**.
- **O que falar:**
  > "Esta é a tela inicial da clínica. Temos 5 pacientes fictícios com barras de progresso, três status em cor e texto e a coluna Acionamento atual: aqui cada membro da equipe sabe quem precisa agir naquela etapa — Recepção, Enfermagem, Anestesista ou Médico executor — com a instrução exata e filtro por papel."
- **Ação:** utilize o filtro **Acionamento** ou clique diretamente em **Atender** na linha de **Marina Ferreira Costa** (`Atenção`).

---

## 35 a 55 segundos — Leitura sem rolagem e intervenção do perfil (B. Detalhe do Paciente)
- **Na tela:** **B. Detalhe do Paciente** (tudo visível sem rolar em `1366×768`).
- **O que falar:**
  > "No detalhe da Marina, toda a linha do tempo e os dados críticos aparecem juntos sem rolagem vertical. O painel sinaliza o alerta informativo de alergia a látex no questionário ausente no sistema. Ao selecionar Enfermagem ou Anestesista, o bloco Painel do perfil mostra quem está acionado e abre o formulário rápido para aferir peso e altura ou conciliar a divergência na própria tela, sem emitir conduta automática."
- **Ação:** alterne o seletor **Perfil** para **Anestesista**, clique em **Registrar / Editar (Anestesista)**, responda **Sim, alergia confirmada** na pergunta da segunda conversa com o paciente, clique em **Salvar registro no painel** (o alerta de látex continua visível, agora marcado como confirmado; para cancelá-lo seria preciso informar o que o paciente disse na segunda conversa) e clique brevemente em **Ver dado bruto (FHIR)**.

---

## 55 a 75 segundos — Questionário leigo simplificado no celular (C. Visão do Paciente)
- **Na tela:** alterne para **Clínica sem sistema (só questionário)** e selecione **Carlos Eduardo Mendes**, acessando **C. Visão do Paciente (Celular)**.
- **O que falar:**
  > "Quando o paciente responde de casa pelo celular, ele não enfrenta termos médicos difíceis: usamos linguagem cotidiana, botões grandes de Sim e Não, chips de um toque e pergunta clara sobre remédio para 'afinar o sangue'. Quando o médico executor conclui a etapa na clínica, as orientações pós-procedimento também ficam acessíveis aqui automaticamente."
- **Ação:** toque em **Preencher respostas de exemplo**, clique em **Enviar questionário** e retorne ao **Quadro da Clínica** para mostrar a atualização em tempo real.

---

## 75 a 90 segundos — Governança e encerramento
- **Na tela:** detalhe atualizado em memória e botões **Iniciar tour** / **Reiniciar demonstração**.
- **O que falar:**
  > "Toda a demonstração usa dados fictícios, não armazena dados fora da memória do navegador e não emite recomendação clínica — mantendo nosso recorte informativo alinhado às cautelas regulatórias da RDC 657/2022 da Anvisa e da LGPD. Nos próximos passos externos, o time — Augusto Linhares, Marcelo Teles e Karina — vai submeter o protocolo clínico à validação de especialistas convidados, conduzir descoberta comercial com 3 clínicas parceiras e testar esta demonstração em campo mirando leitura completa abaixo de 30 segundos com zero digitação adicional. Obrigado."
- **Ação opcional para perguntas:** caso a banca queira explorar passo a passo após a apresentação, acione **Iniciar tour** para percorrer automaticamente os 8 cenários-chave.
