- Aprenda a Utilizar o Gherkin
    - **Gherkin**
        - **Definição**: linguagem estruturada utilizada em BDD (Behavior Driven Development) para descrever o comportamento do sistema de forma clara, legível e focada na regra de negócio. Permite que requisitos sejam escritos em formato executável, servindo tanto como documentação viva quanto como base para testes manuais e automatizados.
            
            **Ex:**
            
            ```
            Cenário: Login com credenciais válidas
              Dado que o usuário está na tela de login
              Quando ele informa e-mail e senha válidos
              Então o sistema deve permitir o acesso ao painel principal
            ```
            
        - É focado na regra de negócio e no comportamento esperado do sistema, escrito em forma de steps (passos), representando a interação do usuário com o sistema e a resposta do sistema.
            
            **Ex:** validar bloqueio após 3 tentativas inválidas de login.
            
        - Não substitui obrigatoriamente todos os casos de teste tradicionais, mas pode substituir casos escritos em formato step-by-step técnico quando adotado como padrão de especificação de comportamento.
            
            **Ex:** ao invés de um documento detalhado com “Passo 1, Passo 2, Passo 3”, utiliza-se cenário estruturado com Given/When/Then.
            
        - **Dado / Given**: representa o contexto inicial, estado do sistema ou pré-condição antes da ação principal.
            
            **Ex:** Dado que o usuário possui cadastro ativo no sistema.
            
        - **Quando / When**: representa a ação principal (gatilho) executada pelo usuário ou sistema.
            
            **Ex:** Quando o usuário informa senha incorreta.
            
        - **Então / Then**: representa o resultado esperado após a ação.
            
            **Ex:** Então o sistema deve exibir a mensagem "Senha inválida".
            
        - **E / And**: utilizado para complementar Given, When ou Then, adicionando informações sem quebrar a estrutura lógica.
            
            **Ex:**
            
            ```
            Dado que o usuário está na tela de login
            E possui cadastro ativo
            Quando informa senha incorreta
            Então o sistema exibe mensagem de erro
            E incrementa o contador de tentativas
            ```
            
        - É importante evitar escrever Gherkin como um roteiro excessivamente detalhado de interface (ex: “clicar no botão azul no canto direito”), pois o foco deve ser comportamento de negócio, não microações técnicas.
        - O **When** é essencial porque representa o evento que provoca a reação do sistema. Boas práticas recomendam apenas **um When principal por cenário**, pois deve haver um único gatilho que gere o resultado validado.
        - O título do cenário deve refletir claramente o comportamento validado no Then, mantendo coerência entre nome do cenário e resultado esperado.
            
            **Ex correto:**
            
            `Cenário: Bloquear usuário após três tentativas inválidas`
            
            O Then deve validar exatamente esse comportamento.
            
        - Boas práticas adicionais:
            - Cada cenário deve testar apenas um comportamento específico.
            - Evitar múltiplos Thens desconectados.
            - Utilizar linguagem clara e próxima ao negócio.
            - Reutilizar steps sempre que possível para manter padronização.
            - Evitar lógica condicional dentro do step (não colocar regras técnicas dentro do texto).
        - Estrutura completa recomendada:
            - Feature: descreve a funcionalidade
            - Scenario: descreve o comportamento específico
            - Given / When / Then / And estruturam o fluxo
            
            **Ex completo:**
            
            ```
            Funcionalidade: Login de usuário
            
              Cenário: Bloqueio após três tentativas inválidas
                Dado que o usuário possui cadastro ativo
                E já realizou duas tentativas inválidas
                Quando ele informa uma senha incorreta novamente
                Então o sistema deve bloquear o usuário por 15 minutos
                E exibir mensagem de bloqueio
            ```
            
    - **Diferenças entre Cucumber, Gherkin e BDD**
        - **BDD:** abordagem de desenvolvimento ágil focada em colaboração entre PO, QA e Dev para definir comportamentos do sistema com base em exemplos concretos antes da implementação. Tem como objetivo alinhar entendimento, reduzir ambiguidades e transformar regras de negócio em especificações claras e testáveis. Não é ferramenta nem linguagem; é um processo colaborativo (ex: dinâmica dos “Three Amigos”). O foco está no comportamento observável do sistema sob a perspectiva do negócio.
            
            **Ex:** regra discutida em refinamento: “Usuário deve ser bloqueado após 3 tentativas inválidas”. O time define exemplos claros de quando ocorre o bloqueio e por quanto tempo.
            
        - **Gherkin:** linguagem estruturada utilizada dentro do BDD para escrever especificações de comportamento em formato padronizado (Feature, Scenario, Given, When, Then). Serve como documentação viva e base para automação. Não executa testes sozinho; apenas descreve comportamento de forma legível e próxima ao negócio. Deve focar em regra de negócio, não em detalhes técnicos de interface.
            
            **Ex:**
            
            ```
            Cenário: Login com credenciais válidas
              Dado que o usuário está na tela de login
              Quando ele informa e-mail e senha válidos
              Então o sistema deve permitir o acesso ao painel principal
            ```
            
        - **Cucumber:** framework de automação que interpreta arquivos escritos em Gherkin e conecta cada step a métodos implementados na linguagem de programação escolhida (Java, JavaScript, etc.), tornando os cenários executáveis. Faz a ponte entre linguagem de negócio (Gherkin) e código de automação (Step Definitions). Sem implementação dos steps, o cenário não executa.
            

            **Ex:** o step `When ele informa senha incorreta` é associado a um método automatizado que executa a ação no sistema via Selenium, Cypress ou outra ferramenta.



