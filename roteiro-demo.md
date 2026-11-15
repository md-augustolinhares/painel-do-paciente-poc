# Roteiro de Demonstração — 90 segundos

Este roteiro acompanha a apresentação ao vivo da prova de conceito (**Painel do Paciente** — *nome provisório*) com dados 100% fictícios. O objetivo da demo é provar uma única tese: **a equipe entende o estado do paciente olhando uma tela só, sem digitar nada a mais.**

> **Dica prática:** Você pode seguir os passos manualmente abaixo ou clicar em **`Iniciar tour`** na barra superior da demonstração para navegar passo a passo com o balão explicativo na tela. Antes de repetir uma apresentação, clique em **`Reiniciar demonstração`**.

---

## Sequência cronometrada (8 passos · 90 segundos)

| Tempo | Passo | O que clicar na tela | O que falar |
|---|---|---|---|
| **00s – 10s** | **1. Quadro da clínica** | Abra a aba **Demonstração (PoC)** → tela **A. Quadro da Clínica**. | *"Cinco pacientes, três status, uma tela. Como um painel de voos, toda a equipe vê em segundos quem está Pronto, quem está Pendente e quem exige Atenção."* |
| **10s – 22s** | **2. A dor no Paciente 3** | Clique na paciente 3 (**Marina Ferreira Costa** — status **Atenção**). | *"Abrindo a Marina: a alergia a látex aparece no questionário do paciente, mas não existe no sistema da clínica. Hoje, com cada profissional no seu prontuário, ninguém veria essa divergência."* |
| **22s – 32s** | **3. Trocar para Anestesista** | No seletor **Perfil**, mude de **Recepção** para **Anestesista**. | *"Cada profissional vê primeiro o que importa para ele. A anestesista bate o olho em alergias, medicações e jejum, sem precisar caçar em outras abas."* |
| **32s – 52s** | **4. Visão do Paciente 2 ao vivo** | Clique em **C. Visão do Paciente (Celular)**, selecione **Carlos Eduardo Mendes**, clique em **Preencher respostas de exemplo** (ou digite os campos) e clique em **Enviar questionário**. | *"Agora no celular do Carlos, que estava pendente: ele responde o questionário rápido pré-procedimento em casa."* |
| **52s – 62s** | **5. Retorno ao Quadro** | Clique em **Voltar ao Quadro** (ou na sub-aba **A. Quadro da Clínica**). | *"O painel atualizou sozinho na hora — etapa avançou e as pendências mudaram. Ninguém da equipe digitou nada a mais."* |
| **62s – 72s** | **6. Cenário sem sistema** | No seletor **Cenário**, troque para **Clínica sem sistema (só questionário)**. | *"E se a clínica pequena não tiver prontuário eletrônico? Funciona mesmo sem sistema: o painel passa a ser alimentado direto pelo questionário do paciente."* |
| **72s – 82s** | **7. Dado bruto (HL7 FHIR)** | Volte o cenário para **Clínica com sistema (FHIR simulado)**, abra um paciente (ex.: **Marina Ferreira Costa**) e clique em **Ver dado bruto (FHIR)**. | *"Quando a clínica já tem sistema, a integração planejada lê apenas dado estruturado no padrão HL7 FHIR — o padrão nacional adotado pela RNDS."* |
| **82s – 90s** | **8. Fechamento** | Feche o modal (**Fechar**) e retorne ao **Quadro da Clínica**. | *"Não trocamos o prontuário de ninguém. Apenas mostramos em uma tela só o que toda a equipe precisa ver para o procedimento."* |

---

## Notas rápidas para o apresentador

- **Pergunta sobre anticoagulante (bônus):** Se perguntarem sobre medicações de risco, abra o paciente 4 (**Roberto Almeida Nascimento**) com o perfil **Anestesista** para mostrar o destaque informativo de uso de anticoagulante (`Apixabana 5 mg`) e a pendência de acompanhante — reforçando que o painel apenas informa e **não dá conduta clínica**.
- **Pergunta sobre pós-procedimento:** Na tela **C. Visão do Paciente (Celular)**, selecione a paciente 5 (**Luciana Ribeiro Campos**) para mostrar as orientações ilustrativas de pós-procedimento no celular (marcadas para validação pela equipe clínica).
- **Pergunta sobre LGPD e Anvisa:** Reforce que a demonstração usa apenas dados fictícios, sem persistência local ou envio para servidores, e que a primeira versão exibe somente alertas informativos (sem recomendação clínica).
