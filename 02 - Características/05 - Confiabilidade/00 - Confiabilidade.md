## Resumo Executivo

A característica **Confiabilidade** segundo a ISO/IEC 25010 avalia o grau em que um sistema, produto ou componente executa funções especificadas sob condições determinadas por um período predefinido. Ela se desdobra em quatro subcaracterísticas — **Maturidade**, **Disponibilidade**, **Tolerância a Falhas** e **Recuperabilidade** — que, em conjunto, permitem projetar, avaliar e melhorar software para operar de forma contínua, minimizando interrupções e garantindo recuperação rápida em caso de falhas ([Wikipédia](https://pt.wikipedia.org/wiki/ISO/IEC_25000 "ISO/IEC 25000 – Wikipédia, a enciclopédia livre")). Para medir Confiabilidade, emprega-se métricas como MTBF (Mean Time Between Failures), disponibilidade percentual (uptime), testes de injeção de falhas (chaos engineering) e MTTR (Mean Time To Recover), conforme orientações da ISO/IEC 25023 ([ISO](https://www.iso.org/standard/35747.html?utm_source=chatgpt.com "ISO/IEC 25023:2016 - Systems and software engineering")). No estudo de caso da Netflix, observou-se que, mesmo sob cargas extremas e falhas simuladas, a Disponibilidade de requisições críticas permaneceu acima de 99,4% graças a práticas avançadas de tolerância a falhas e chaos engineering ([Netflix TechBlog](https://netflixtechblog.com/enhancing-netflix-reliability-with-service-level-prioritized-load-shedding-e735e6ce8f7d?utm_source=chatgpt.com "Enhancing Netflix Reliability with Service-Level Prioritized Load ...")) ([IEEE Computer Society](https://www.computer.org/publications/tech-news/research/realizing-software-reliability-in-the-face-of-infrastructure-instability/?utm_source=chatgpt.com "How Netflix Adopted the New Mindset of Software Failure as the ...")).

---

## O que diz a característica?

A **Confiabilidade** é definida pela ISO/IEC 25010 como o “grau para o qual um sistema, produto ou componente executa funções especificadas sob condições especificadas por um período de tempo especificado” ([Wikipédia](https://pt.wikipedia.org/wiki/ISO/IEC_25000 "ISO/IEC 25000 – Wikipédia, a enciclopédia livre")). Ela é composta por quatro subcaracterísticas:

1. **Maturidade**  
    Avalia a prontidão do sistema para enfrentar condições adversas com baixo índice de falhas, refletido em métricas como taxa de defeitos em produção ([Codacy Blog](https://blog.codacy.com/iso-25010-software-quality-model?utm_source=chatgpt.com "An Exploration of the ISO/IEC 25010 Software Quality Model")).
    
2. **Disponibilidade**  
    Mede a proporção de tempo em que o sistema permanece operacional e acessível ao usuário final, normalmente expressa em percentuais de uptime (por exemplo, 99,9%) ([Wikipedia](https://en.wikipedia.org/wiki/Reliability%2C_availability_and_serviceability?utm_source=chatgpt.com "Reliability, availability and serviceability")).
    
3. **Tolerância a Falhas**  
    Verifica a capacidade do sistema de continuar operando corretamente na presença de falhas de hardware ou software, por meio de mecanismos como redundância e degradative behavior control ([SIG](https://softwareimprovementgroup.com/wp-content/uploads/SIG-Evaluation-Criteria-Reliability-Guidance-for-producers-2.0.pdf?utm_source=chatgpt.com "[PDF] SIG EVALUATION CRITERIA RELIABILITY")).
    
4. **Recuperabilidade**  
    Indica quão rápido e eficientemente o sistema pode restaurar seu estado desejado após uma falha, usando estratégias de fail-over ou recuperação assistida ([Agilitest](https://www.agilitest.com/cards/reliability-testing?utm_source=chatgpt.com "Reliability testing | Agility Maturity Cards by Agilitest")).
    

---

## Como observar e medir em um software?

Para avaliar e quantificar a Confiabilidade, recomenda-se combinar práticas de monitoramento contínuo, métricas padronizadas e testes dinâmicos:

- **Maturidade**
    
    - **Métrica**: Taxa de falhas por milhão de operações ou defeitos em produção.
        
    - **Método de coleta**: Ferramentas de APM (Application Performance Management) e análise de logs de produção para contagem de incidentes ([SIG](https://softwareimprovementgroup.com/wp-content/uploads/SIG-Evaluation-Criteria-Reliability-Guidance-for-producers-2.0.pdf?utm_source=chatgpt.com "[PDF] SIG EVALUATION CRITERIA RELIABILITY")).
        
- **Disponibilidade**
    
    - **Métrica**: Uptime percentual = (Tempo Total de Operação / Tempo Total Planejado) × 100.
        
    - **Ferramentas**: Monitores de disponibilidade (Pingdom, UptimeRobot) que registram interrupções e calculam SLAs ([Wikipedia](https://en.wikipedia.org/wiki/Reliability%2C_availability_and_serviceability?utm_source=chatgpt.com "Reliability, availability and serviceability")).
        
- **Tolerância a Falhas**
    
    - **Métrica**: Cobertura de falhas toleradas = (Número de falhas mascaradas / Total de falhas injetadas).
        
    - **Técnica**: Chaos engineering — injeção de falhas controladas usando frameworks como Netflix Simian Army para validar a resiliência ([IEEE Computer Society](https://www.computer.org/publications/tech-news/research/realizing-software-reliability-in-the-face-of-infrastructure-instability/?utm_source=chatgpt.com "How Netflix Adopted the New Mindset of Software Failure as the ...")).
        
- **Recuperabilidade**
    
    - **Métrica**: MTTR (Mean Time To Recover) — tempo médio para restaurar o serviço após defeito.
        
    - **Prática**: Drill de incidentes e playbooks de recuperação para cronometrar intervenções e automatizar rollback ([Agilitest](https://www.agilitest.com/cards/reliability-testing?utm_source=chatgpt.com "Reliability testing | Agility Maturity Cards by Agilitest")).
        

Adicionalmente, a ISO/IEC 25023 fornece um guia de medidas específicas para cada característica, permitindo alinhar as métricas ao modelo de qualidade do software ([ISO](https://www.iso.org/standard/35747.html?utm_source=chatgpt.com "ISO/IEC 25023:2016 - Systems and software engineering")).

---

## Estudo de Caso: Netflix

### Contexto e Observações

A Netflix, operando em AWS, adota uma abordagem de **Chaos Engineering** para validar a Confiabilidade de seus serviços. Em 2024, após implementar _prioritized load-shedding_, observou-se:

> “Apesar de impor throttling em mais de 50% das requisições, a disponibilidade das requisições iniciadas pelo usuário permaneceu acima de 99,4%” ([Netflix TechBlog](https://netflixtechblog.com/enhancing-netflix-reliability-with-service-level-prioritized-load-shedding-e735e6ce8f7d?utm_source=chatgpt.com "Enhancing Netflix Reliability with Service-Level Prioritized Load ...")).

Isso demonstra alta **Disponibilidade** e eficaz **Tolerância a Falhas**, pois apenas processos de pré-fetch sofreram degradação propositalmente, preservando a experiência principal.

### Como Foi Medido

1. **Chaos Experiments**: Uso do _Simian Army_ para simular quedas de região e indisponibilidade de servidores (Chaos Kong, Chaos Monkey), medindo o impacto nos KPIs de disponibilidade ([IEEE Computer Society](https://www.computer.org/publications/tech-news/research/realizing-software-reliability-in-the-face-of-infrastructure-instability/?utm_source=chatgpt.com "How Netflix Adopted the New Mindset of Software Failure as the ...")).
    
2. **Monitoramento de Uptime**: Ferramentas internas que comparam latência e taxa de erro em endpoints críticos antes e depois das injeções de falha.
    
3. **Métricas de Recuperação**: Registros de MTTR em incidentes reais, com rodadas de drills para otimizar playbooks de restauração.
    

### Pontos Fortes e Fracos

|Aspecto|Pontos Fortes|Pontos Fracos|
|---|---|---|
|**Maturidade**|Ambiente cuidadosamente testado em produção, baixa taxa de falhas não percebidas pelo usuário.|Exige elevado investimento em automação de testes e pipelines de CI/CD robustos.|
|**Disponibilidade**|SLA interno > 99,9% em endpoints críticos; implantação de _load shedding_ seletivo mantém serviços essenciais sempre ativos.|Monitoramento e alertas complexos; risco de falsos positivos que podem gerar alertas desnecessários.|
|**Tolerância a Falhas**|Mecanismos de redundância e fallback granulares (e.g., buckets de prioridade) permitem continuar operando mesmo sob condições adversas.|A complexidade arquitetural cresce conforme se introduzenses camadas de resiliência; difícil de gerenciar em larga escala.|
|**Recuperabilidade**|Playbooks e “simulações de incidente” frequentes reduzem MTTR a minutos, com rollbacks automatizados e intervenção humana guiada por runbooks.|Requer equipe treinada e disciplinada para executar drills; automação incompleta pode atrasar a restauração manual.|

---

**Conclusão**  
A Confiabilidade, conforme a ISO/IEC 25010, é essencial para garantir que sistemas críticos atendam às expectativas de operação contínua. A combinação de métricas objetivas (MTBF, MTTR, uptime), práticas de chaos engineering e ferramentas de monitoramento contínuo fornece um caminho claro para projetar, avaliar e aprimorar a Maturidade, Disponibilidade, Tolerância a Falhas e Recuperabilidade de qualquer software.