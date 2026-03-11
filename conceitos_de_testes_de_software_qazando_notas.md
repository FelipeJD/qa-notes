- **Conceitos de Testes de Software**
    - **Erro, Defeito e Falha**
        - **Erro**: ação humana incorreta durante o desenvolvimento do software. Pode ser sintático (erro de escrita no código) ou semântico (lógica implementada incorretamente).
            
            **Ex:** desenvolvedor implementa `if (idade > 18)` quando a regra correta era `>= 18`.
            
        - **Defeito**: problema no código ou no sistema causado por um erro, fazendo com que o comportamento real seja diferente do esperado (deveria funcionar de forma X, mas funciona de Y).
            
            **Ex:** sistema bloqueia usuários com exatamente 18 anos.
            
        - **Falha**: manifestação visível de um defeito durante a execução do sistema, percebida pelo usuário.
            
            **Ex:** usuário de 18 anos tenta se cadastrar e recebe mensagem de “idade inválida”.
            
    - **Scrum x Kanban**
        - **Scrum**: framework ágil estruturado em sprints com duração fixa, papéis definidos (PO, Scrum Master, Dev Team) e cerimônias formais (planning, daily, review, retrospectiva).
            
            **Ex:** equipe trabalha em ciclos de 2 semanas entregando incremento ao final de cada sprint.
            
        - **Kanban**: método baseado em fluxo contínuo, com limitação de tarefas em andamento (WIP), sem iterações fixas obrigatórias e sem papéis formais.
            
            **Ex:** tarefas entram continuamente no quadro e avançam pelas colunas “A fazer”, “Em andamento” e “Concluído”.
            
    - **Níveis de Teste**
        - **Testes de unidade / unitários**: realizados na menor unidade testável do código (função, método, classe), geralmente executados por desenvolvedores.
            
            **Ex:** testar isoladamente a função `calcularDesconto()`.
            
        - **Testes de integração**: verificam se dois ou mais módulos/serviços interagem corretamente entre si.
            
            **Ex:** validar se o sistema envia corretamente os dados para o gateway de pagamento.
            
        - **Testes de sistema**: avaliam o sistema como um todo, validando requisitos funcionais e não funcionais em ambiente próximo ao real.
            
            **Ex:** realizar o fluxo completo de compra em um e-commerce.
            
        - **Testes de aceitação**: validam se o sistema atende aos critérios de aceitação definidos pelo negócio, normalmente executados pelo cliente ou Product Owner.
            
            **Ex:** PO valida se a nova regra de frete atende ao requisito acordado.
            
    - **Tipos de Teste**
        - **Testes de caixa branca**: baseados no conhecimento da estrutura interna do código.
            
            **Ex:** testar todos os caminhos condicionais de uma função com múltiplos `if/else`.
            
        - **Testes de caixa preta**: avaliam o comportamento do sistema sem considerar sua implementação interna.
            
            **Ex:** validar login com credenciais válidas e inválidas.
            
        - **Testes funcionais**: verificam se o sistema executa as funcionalidades conforme requisitos e documentação.
            
            **Ex:** testar se o botão “Finalizar compra” conclui o pedido corretamente.
            
        - **Testes não funcionais**: avaliam características como desempenho, segurança, escalabilidade e usabilidade.
            
            **Ex:** medir se a página carrega em até 2 segundos.
            
        - **Testes de regressão**: garantem que alterações ou correções não impactaram funcionalidades já existentes.
            
            **Ex:** após corrigir bug no carrinho, reexecutar testes de cadastro e login.
            
        - **Testes de usabilidade**: avaliam a experiência do usuário ao utilizar o sistema.
            
            **Ex:** observar usuários tentando finalizar uma compra e identificar dificuldades.
            
        - **Testes de segurança**: identificam vulnerabilidades simulando ataques ou acessos indevidos.
            
            **Ex:** testar tentativa de SQL Injection no campo de login.
            
        - **Testes de performance**: medem desempenho sob diferentes cargas e condições de uso.
            
            **Ex:** simular 1.000 usuários simultâneos acessando o sistema.
            
        - **Testes de compatibilidade**: verificam funcionamento em diferentes navegadores, dispositivos, sistemas operacionais ou versões.
            
            **Ex:** testar aplicação no Chrome, Firefox e Safari em desktop e mobile.
            
    - **Técnicas de Teste**
        - **Partição de equivalência**: divide dados de entrada em classes onde todos os valores de uma classe têm o mesmo comportamento. Testa-se um representante de cada classe válida e inválida.
            
            **Ex:** campo aceita números de 1 a 10 → testar 5 (válido), 0 (inválido) e 11 (inválido).
            
        - **Análise de valor limite**: foca nos pontos de transição entre classes válidas e inválidas, pois é onde erros ocorrem com maior frequência.
            
            **Ex:** campo aceita números de 1 a 10 → testar 0, 1, 10 e 11.
            
        - **Teste de caso de uso**: valida o sistema com base nos fluxos principal, alternativos e de exceção descritos em um caso de uso.
            
            **Ex:** no caso de uso *Login*, testar acesso válido (fluxo principal) e combinações com usuário ou senha inválidos.
            
        - **Tabela de decisão**: utilizada quando o comportamento depende de combinações de múltiplas condições, organizadas em formato de tabela para garantir cobertura das regras de negócio.
            
            **Ex:** sistema concede desconto apenas se cliente for VIP **e** compra > R$ 200; cada combinação gera um caso de teste.
            
        - **Testes de mutação**: avaliam a qualidade da suíte de testes ao introduzir pequenas alterações artificiais no código para verificar se os testes detectam a mudança.
            
            **Ex:** alterar `>` para `>=` e verificar se algum teste falha.
            
        - **Testes exploratórios**: realizados sem roteiro detalhado prévio, combinando aprendizado, execução e análise simultaneamente.
            
            **Ex:** explorar uma nova funcionalidade recém-implementada simulando comportamento real do usuário.
            
    - **Testes Automatizados**
        - **Testes automatizados**: utilizam scripts e ferramentas para executar casos de teste automaticamente, garantindo repetibilidade, velocidade e confiabilidade, especialmente em regressões.
            
            **Ex:** executar automaticamente testes de login a cada novo deploy.
            
    - **Reporte de Bugs**
        - **Severidade dos bugs**: métrica que classifica o impacto técnico do defeito no sistema (Alta, Média, Baixa), indicando o nível de criticidade e priorização de correção.
            
            *Objetivo:* entender o risco técnico acumulado e o impacto no produto.
            
        - **Quantidade de bugs por causa raiz (Root Cause Analysis – RCA)**: mede a distribuição dos defeitos conforme sua origem (ex: lógica incorreta, crash, ambiente, documentação).
            
            *Objetivo:* identificar padrões e atacar a origem recorrente dos problemas.
            
        - **Front ou Back (Origem do bug)**: classifica se o defeito está relacionado ao Front-end ou Back-end.
            
            *Objetivo:* mapear onde estão concentrados os problemas e orientar melhoria técnica no time.
            
        - **Horas gastas por causa raiz**: mede o tempo investido na correção dos bugs conforme sua origem.
            
            *Objetivo:* avaliar custo de retrabalho e identificar causas que geram maior esforço de manutenção.
            
        - **Quantidade de bugs abertos (regra de acompanhamento / régua)**: indicador de volume de defeitos ativos, geralmente associado a faixas de controle (ex: até 3 sem problema, 3 a 5 alerta, acima de 10 crítico).
            
            *Objetivo:* monitorar saúde do produto e necessidade de ações corretivas estruturais.
            
    - **Relatório de bugs / defeitos para alinhamento com o time**
        - O relatório de bugs deve ser usado como ferramenta de melhoria contínua do processo, ajudando o time a identificar padrões, gargalos e oportunidades de prevenção de defeitos, otimizando o uso do tempo e esforço técnico.
        - O foco do relatório deve ser sempre no processo e na causa raiz, nunca na responsabilização individual. A análise deve responder “por que isso aconteceu?” e “como evitamos que aconteça novamente?”, e não “quem errou?”.
        - A categorização correta dos bugs é essencial para gerar métricas úteis. Classificações como severidade, prioridade, causa raiz, área impactada (Front/Back), tipo de defeito e ambiente onde foi encontrado tornam a análise mais precisa e orientada à ação.
        - Métricas consolidadas ajudam na definição de prioridades estratégicas, permitindo atacar causas recorrentes (ex: falhas frequentes de regra de negócio ou problemas de validação). A análise de causa raiz (RCA) é fundamental para reduzir reincidência.
        - Quantidade de bugs não deve ser analisada isoladamente. É importante relacionar volume de defeitos com esforço de correção (horas gastas), impacto no negócio e severidade. Um único bug crítico que consome muitas horas ou impacta produção pode ser mais relevante que diversos bugs triviais.
        - Defeitos identificados em ambiente de testes são considerados positivos do ponto de vista de qualidade preventiva (shift-left), pois evitam impacto no usuário final. Já bugs encontrados em produção devem ser monitorados com maior criticidade, pois impactam diretamente o negócio e a reputação do produto.
        - Indicadores importantes em relatórios de bugs incluem: taxa de reabertura de bugs, tempo médio de resolução (MTTR), taxa de defeitos por release, distribuição por severidade e percentual de defeitos encontrados em produção vs testes.
        - Relatórios e dashboards devem ser adaptados ao contexto do projeto, maturidade do time e objetivos estratégicos. Times em fase inicial podem focar em volume e severidade; times maduros podem focar em previsibilidade, prevenção e redução de retrabalho.
        - O objetivo final de um relatório de bugs não é medir produtividade individual, mas aumentar a qualidade do produto, reduzir retrabalho, melhorar previsibilidade e fortalecer a tomada de decisão baseada em dados.
    - **Auxílio da IA para QA**
        - Utilizar prompts claros e minimamente detalhados, definindo o papel da IA (ex: atuar como especialista em testes de software, QA sênior, analista de qualidade), o contexto do sistema e o objetivo esperado (gerar cenários, casos de teste, matriz de decisão, etc.).
            
            **Ex:** “Atue como um especialista em testes de software. Vou enviar os detalhes de uma tela de login e suas regras de negócio. Gere o máximo de cenários de teste possíveis no formato Gherkin, incluindo fluxo principal, alternativos, exceções e casos de borda.”
            
        - Fornecer o máximo de contexto possível sobre a funcionalidade: descrição da tela, campos existentes, validações, mensagens de erro esperadas, integrações envolvidas, ambiente (web, mobile, API).
            
            **Ex:** “A tela possui os campos e-mail e senha, e botão de login. O e-mail deve ter formato válido. A senha deve ter no mínimo 8 caracteres. Após 3 tentativas inválidas, o usuário deve ser bloqueado por 15 minutos.”
            
        - Enviar regras de negócio de forma estruturada e detalhada, evitando ambiguidades. Quanto mais clara a regra, mais precisos serão os cenários gerados.
            
            **Ex:** “Usuários com perfil administrador podem acessar o painel mesmo com senha expirada. Usuários comuns devem redefinir a senha antes de acessar.”
            
        - Utilizar imagens da interface quando necessário, solicitando que a IA identifique elementos da tela e possíveis pontos de validação.
            
            **Ex:** enviar screenshot da tela e pedir: “Identifique campos obrigatórios e possíveis validações que devem ser testadas.”
            
        - Solicitar diferentes perspectivas de teste, como:
            - Casos positivos e negativos
            - Testes de limite
            - Testes de segurança
            - Testes exploratórios sugeridos
            - Cenários de regressão
        - Validar criticamente a saída da IA antes de utilizar os cenários em produção. A IA auxilia na geração de ideias, mas não substitui análise técnica e conhecimento do contexto do produto.
        - Utilizar a IA também para:
            - Revisar casos de teste existentes
            - Melhorar clareza de bugs reportados
            - Gerar exemplos de massa de dados
            - Criar cenários automatizados (Gherkin, Cypress, Selenium, etc.)
            - Ajudar na análise de causa raiz a partir de logs ou descrição de falhas
        - Evitar compartilhar dados sensíveis ou informações confidenciais do projeto ao utilizar ferramentas de IA externas.
        - Encarar a IA como ferramenta de apoio à produtividade e brainstorming técnico, não como substituição da responsabilidade do QA.