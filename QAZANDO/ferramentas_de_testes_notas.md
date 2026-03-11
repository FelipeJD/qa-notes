- **Ferramentas de Testes**

    - Trello é uma ferramenta semelhante ao ADTraffic, voltada para gestão de tarefas e organização visual de fluxos (Kanban), focada em acompanhamento e organização do trabalho, não em gestão de testes.
    - QASE é uma ferramenta de gestão de testes, com recursos específicos para testes de software (casos de teste, suítes, execuções e relatórios). O Xray se enquadra na mesma categoria, porém é integrado diretamente ao Jira, oferecendo rastreabilidade mais nativa e sendo bastante comum no mercado, valendo a pena explorá-lo.
    - Jira é uma ferramenta de gestão de projetos, tarefas e bugs, amplamente utilizada em times ágeis. Possui integração com Trello e QASE. Para o QA, o combo Jira + QASE é um foco interessante para rotina prática em ferramentas separadas. Já o combo Jira + Xray costuma ser mais indicado por integrar testes diretamente ao Jira (Xray é o plugin de testes dentro do Jira) e ser uma combinação frequentemente exigida em vagas.
    - NO QASE há como compartilhar um report de Test Run que a pessoa pode acessar mesmo sem conta
    - No Jira, podem ser criadas Histórias num Backlog (reforçar metodologia scrum)
        - **Definição:** descrição curta de uma necessidade do usuário/cliente, escrita sob a perspectiva de quem utiliza o sistema. Representa o valor que deve ser entregue e ajuda o time a entender o que precisa ser desenvolvido.
            
            **Ex:**
                
                Como usuário cadastrado
                    
                Quero recuperar minha senha
                    
                Para conseguir acessar minha conta novamente
                    
        - **Insights**
            - Foca em comportamento e valor, não em implementação técnica
            - Fica no Product Backlog e pode ser planejada em Sprints
            - Deve ser clara o suficiente para permitir discussão entre PO, Dev e QA
            - Normalmente é complementada por critérios de aceitação e regras de negócio
            
            **Ex:**
            
                História: recuperar senha
            
                Critérios de aceitação: validar e-mail existente, enviar link, expiração do link etc.
        - **Exemplo prático (formato comum no dia a dia)**
            
            **Ex:**
            
            **Título:**
            
            Recuperação de senha
            
            **Descrição (história):**
                    
                    Como usuário cadastrado
                    
                    Quero solicitar redefinição de senha
                    
                    Para recuperar acesso à minha conta
                    
            **Critérios de aceitação:**
            
                    Deve enviar e-mail com link de redefinição
                
                    Link expira em 30 minutos
            
                    Exibir mensagem de sucesso após solicitação
    - No Jira, é possível arrastar as histórias do Backlog > Sprint na aba **Backlog**, e ela será exibida no **Painel**