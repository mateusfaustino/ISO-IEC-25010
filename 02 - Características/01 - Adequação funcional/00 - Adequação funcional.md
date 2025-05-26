	A característica **Adequação Funcional** da ISO/IEC 25010 refere-se ao grau em que as funcionalidades de um produto ou sistema atendem às necessidades explícitas e implícitas dos seus usuários quando usados em condições especificadas ([ISO 25000 Portal](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010?utm_source=chatgpt.com "ISO/IEC 25010")). Esse atributo é fundamental para garantir que o software entregue valor ao usuário, não apenas existindo, mas executando exatamente o que dele se espera ([Perforce](https://www.perforce.com/blog/qac/what-is-iso-25010?utm_source=chatgpt.com "What Is ISO 25010? | Perforce Software")). A seguir, apresentamos o que diz a norma, como observá-la e medi-la em projetos reais e um estudo de caso ilustrativo.

## O que diz a característica?

A Adequação Funcional representa o grau em que um produto ou sistema fornece funções que satisfazem necessidades declaradas e implícitas sob condições de uso definidas ([ISO 25000 Portal](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010?utm_source=chatgpt.com "ISO/IEC 25010")).  
Essa característica é subdividida em três **sub-características** principais:

- **Completude Funcional**: grau em que o conjunto de funções cobre todas as tarefas especificadas e os objetivos pretendidos dos usuários ([ISO 25000 Portal](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010?utm_source=chatgpt.com "ISO/IEC 25010")).
    
- **Correção Funcional**: grau em que um produto ou sistema fornece resultados precisos e corretos quando utilizado pelos usuários esperados ([ISO 25000 Portal](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010?utm_source=chatgpt.com "ISO/IEC 25010")).
    
- **Adequação Funcional (Appropriateness)**: grau em que as funções facilitam a realização das tarefas e objetivos especificados, tornando o uso eficiente e intuitivo ([ISO 25000 Portal](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010?utm_source=chatgpt.com "ISO/IEC 25010")).
    

## Como observar e medir em um software?

Observar e medir a Adequação Funcional envolve tanto métricas objetivas quanto avaliações subjetivas:

1. **Cobertura de Requisitos (Functional Completeness)**
    
    - **Métrica**: Razão entre o número de funcionalidades implementadas e testadas e o número total de requisitos funcionais definidos.
        
    - **Como medir**: Use rastreamento de requisitos (traceability matrix) para verificar se cada requisito possui pelo menos um caso de teste associado e se esses testes foram executados com sucesso ([VALA](https://www.valagroup.com/wp-content/uploads/2021/12/software-qualit_53686470-compressed.pdf?utm_source=chatgpt.com "[PDF] software quality guidelines - VALA")).
        
2. **Taxa de Sucesso em Testes Funcionais (Functional Correctness)**
    
    - **Métrica**: Percentual de casos de teste funcionais aprovados em relação ao total executado.
        
    - **Como medir**: Ferramentas de automação de testes (por exemplo, Selenium, JUnit) podem gerar relatórios de resultados, permitindo calcular a taxa de aprovação e identificar defeitos remanescentes ([joiv.org](https://joiv.org/index.php/joiv/article/download/2441/816?utm_source=chatgpt.com "[PDF] Software Quality Measurement for Functional Suitability ...")).
        
3. **Índice de Satisfação e Efetividade (Functional Appropriateness)**
    
    - **Métrica**: Resultado de pesquisas de satisfação de usuários (p. ex., Net Promoter Score, avaliações via questionários de aceitação) e taxa de conclusão de tarefas em testes de usabilidade.
        
    - **Como medir**: Conduza entrevistas, testes de aceitação e observação direta do usuário em cenários reais de uso, registrando se os usuários conseguem completar tarefas sem assistência ([Vishen Gounden](https://vishen.co.za/blog/building-the-right-thing/?utm_source=chatgpt.com "Building the right thing - Functional Suitability in Software Quality")).
        
4. **Métodos de Priorização de Funcionalidades**
    
    - **Técnica**: Analytical Hierarchy Process (AHP) para ponderar a importância de cada sub-característica segundo diferentes stakeholders (especialistas, desenvolvedores, usuários) ([ResearchGate](https://www.researchgate.net/publication/377391729_Software_Quality_Measurement_for_Functional_Suitability_Performance_Efficiency_and_Reliability_Characteristics_Using_Analytical_Hierarchy_Process?utm_source=chatgpt.com "(PDF) Software Quality Measurement for Functional Suitability ...")).
        
    - **Como aplicar**: Estruture um questionário, atribua pesos via AHP e calcule um índice composto de qualidade funcional, oferecendo uma visão balanceada entre completude, correção e adequação.
        

## Estudo de caso: ITS Academic Information System

### Contexto

O ITS Academic Information System é uma plataforma universitária para gerenciamento de currículos, matrícula e notas, usada por alunos, professores e administradores.

### O que foi observado

- **Completude Funcional**: todas as funções de matrícula e consulta de notas estavam implementadas conforme especificado no escopo inicial do projeto ([ResearchGate](https://www.researchgate.net/publication/377391729_Software_Quality_Measurement_for_Functional_Suitability_Performance_Efficiency_and_Reliability_Characteristics_Using_Analytical_Hierarchy_Process?utm_source=chatgpt.com "(PDF) Software Quality Measurement for Functional Suitability ...")).
    
- **Correção Funcional**: validações de entrada (p. ex., número de matrícula, horários de aulas) apresentaram menos de 2% de falhas em testes automatizados de rotina ([joiv.org](https://joiv.org/index.php/joiv/article/download/2441/816?utm_source=chatgpt.com "[PDF] Software Quality Measurement for Functional Suitability ...")).
    
- **Adequação Funcional**: em testes de aceitação com 30 alunos, 90% conseguiram concluir tarefas (matrícula, ver notas) sem ajuda em menos de 3 minutos ([ResearchGate](https://www.researchgate.net/publication/377391729_Software_Quality_Measurement_for_Functional_Suitability_Performance_Efficiency_and_Reliability_Characteristics_Using_Analytical_Hierarchy_Process?utm_source=chatgpt.com "(PDF) Software Quality Measurement for Functional Suitability ...")).
    

### Como seria medido

1. **Matriz de rastreabilidade**: documentar todos os requisitos funcionais e vincular a casos de teste, verificando cobertura de 100%.
    
2. **Automação de testes**: executar diariamente suítes de testes funcionais para medir taxa de aprovação e tempo de resposta.
    
3. **Pesquisa de satisfação**: aplicar questionários pós-uso para calcular um índice de satisfação médio ≥ 4 em escala de 1–5.
    

### Pontos fortes e fracos

**Fortes**

- Alta **completude**: todas as funcionalidades principais implementadas.
    
- Boa **correção**: baixa incidência de erros funcionais em produção.
    
- Adequada **usabilidade funcional**: tarefas comuns concluídas rapidamente pelos usuários.
    

**Fracos**

- Falta de funcionalidades avançadas (ex.: integração com sistemas de pagamento), o que reduz a **completude** para determinados perfis de usuário.
    
- Alguns fluxos de exceção (p. ex., alteração de matrícula após prazo) não estavam cobertos nos testes, impactando a **correção** em cenários não ideais.
    
- Interfaces de configuração para administradores pouco intuitivas, afetando a **adequação** em casos de uso raros.
    

---

Este panorama evidencia como a Adequação Funcional é um pilar central para a qualidade de software, exigindo tanto métricas objetivas (cobertura, testes automatizados) quanto feedback contínuo dos usuários para assegurar que o sistema não só funcione, mas funcione da maneira certa.