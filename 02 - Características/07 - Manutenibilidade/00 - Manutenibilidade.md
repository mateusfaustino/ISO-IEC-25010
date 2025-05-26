## Resumo

A **Manutenibilidade** na ISO/IEC 25010 é a capacidade de um software ser modificado de forma eficaz e eficiente para correções, melhorias ou adaptações a mudanças de requisitos e ambiente. Ela se desdobra em cinco sub-características: **Modularidade**, **Reusabilidade**, **Analisabilidade**, **Modificabilidade** e **Testabilidade** ([Perforce](https://www.perforce.com/blog/qac/what-is-iso-25010?utm_source=chatgpt.com "What Is ISO 25010? | Perforce Software")). Para medi-las, usa-se a ISO/IEC 25023, que define métricas como acoplamento, complexidade ciclomática, cobertura de testes e duplicação de código ([Iteh Standards](https://cdn.standards.iteh.ai/samples/35747/34b91bc957f647ce8bbb2093907d7bc0/ISO-IEC-25023-2016.pdf?utm_source=chatgpt.com "[PDF] INTERNATIONAL STANDARD ISO/IEC 25023"), [CISQ](https://www.it-cisq.org/standards/related-standards-and-guidelines/?utm_source=chatgpt.com "Related Standards and Guidelines - CISQ")). No estudo de caso de uma aplicação Spring Boot analisada com SonarQube, observou-se um índice de manuten-ibilidade classificado como “B”, 35 code smells e dívida técnica estimada em 10 dias-homem, revelando pontos fortes na modularidade e cobertura de testes, mas fragilidades em complexidade de algumas classes e falta de documentação em trechos críticos ([Medium](https://medium.com/%40dulanjayasandaruwan1998/enhancing-code-quality-in-spring-boot-applications-with-sonarqube-a3c2c04e31c1?utm_source=chatgpt.com "Enhancing Code Quality in Spring Boot Applications with SonarQube"), [triology.de](https://www.triology.de/en/blog/static-code-analysis-with-sonarqube?utm_source=chatgpt.com "Static code analysis with SonarQube - TRIOLOGY GmbH")).

---

## O que diz a característica?

A **Manutenibilidade** é definida como “o grau de eficácia e eficiência com que um produto ou sistema pode ser modificado para corrigir defeitos, melhorar o desempenho ou adaptá-lo a mudanças no ambiente e nos requisitos” ([TIOBE](https://tiobe.com/files/TIOBETUViTTrustedProductMaintainability_v1_2.pdf?utm_source=chatgpt.com "[PDF] Trusted Product Maintainability - TIOBE")). Ela envolve cinco sub-características:

1. **Modularidade**  
    Grau em que o sistema é composto por componentes discretos, de modo que mudanças em um módulo tenham impacto mínimo nos demais ([Perforce](https://www.perforce.com/blog/qac/what-is-iso-25010?utm_source=chatgpt.com "What Is ISO 25010? | Perforce Software")).
    
2. **Reusabilidade**  
    Grau em que um ativo (por exemplo, uma biblioteca ou componente) pode ser usado em mais de um sistema ou para construir outros ativos ([Perforce](https://www.perforce.com/blog/qac/what-is-iso-25010?utm_source=chatgpt.com "What Is ISO 25010? | Perforce Software")).
    
3. **Analisabilidade**  
    Eficácia e eficiência para avaliar o impacto de uma mudança planejada, diagnosticar falhas ou identificar partes a serem modificadas ([Perforce](https://www.perforce.com/blog/qac/what-is-iso-25010?utm_source=chatgpt.com "What Is ISO 25010? | Perforce Software")).
    
4. **Modificabilidade**  
    Capacidade de efetuar modificações sem introduzir defeitos ou degradar a qualidade existente ([Perforce](https://www.perforce.com/blog/qac/what-is-iso-25010?utm_source=chatgpt.com "What Is ISO 25010? | Perforce Software")).
    
5. **Testabilidade**  
    Eficácia e eficiência para estabelecer critérios de teste e executar testes que confirmem se esses critérios foram atendidos ([Perforce](https://www.perforce.com/blog/qac/what-is-iso-25010?utm_source=chatgpt.com "What Is ISO 25010? | Perforce Software")).
    

---

## Como observar e medir em um software?

A medição da Manutenibilidade baseia-se em métricas que mapeiam cada sub-característica, conforme descrito na ISO/IEC 25023 ([Iteh Standards](https://cdn.standards.iteh.ai/samples/35747/34b91bc957f647ce8bbb2093907d7bc0/ISO-IEC-25023-2016.pdf?utm_source=chatgpt.com "[PDF] INTERNATIONAL STANDARD ISO/IEC 25023"), [CISQ](https://www.it-cisq.org/standards/related-standards-and-guidelines/?utm_source=chatgpt.com "Related Standards and Guidelines - CISQ")). Exemplos de medidas comuns:

- **Acoplamento entre módulos** (modularidade): número médio de dependências entre classes ou pacotes ([arXiv](https://arxiv.org/pdf/2108.02921?utm_source=chatgpt.com "[PDF] The Applicability of ISO/IEC 25023 Measures to the Integration of ...")).
    
- **Complexidade ciclomática** (analisabilidade/modificabilidade): quantidade de caminhos independentes em métodos, identificada por ferramentas como SonarQube ou CodeScene ([docs.sonarsource.com](https://docs.sonarsource.com/sonarqube-cloud/digging-deeper/metric-definitions/?utm_source=chatgpt.com "Understanding measures and metrics | SonarQube Cloud ...")).
    
- **Cobertura de testes** (testabilidade): percentual de linhas ou ramos cobertos por testes automatizados ([docs.sonarsource.com](https://docs.sonarsource.com/sonarqube-cloud/digging-deeper/metric-definitions/?utm_source=chatgpt.com "Understanding measures and metrics | SonarQube Cloud ...")).
    
- **Duplicação de código** (reusabilidade/modularidade): proporção de linhas duplicadas que dificultam manutenção ([docs.sonarsource.com](https://docs.sonarsource.com/sonarqube-cloud/digging-deeper/metric-definitions/?utm_source=chatgpt.com "Understanding measures and metrics | SonarQube Cloud ...")).
    
- **Dívida técnica** (modificabilidade): estimativa de esforço para corrigir “code smells” ou violações de regras de qualidade ([triology.de](https://www.triology.de/en/blog/static-code-analysis-with-sonarqube?utm_source=chatgpt.com "Static code analysis with SonarQube - TRIOLOGY GmbH")).
    
- **Comentário e documentação** (analisabilidade): relação entre linhas de comentário e linhas de código ([triology.de](https://www.triology.de/en/blog/static-code-analysis-with-sonarqube?utm_source=chatgpt.com "Static code analysis with SonarQube - TRIOLOGY GmbH")).
    

Ferramentas como SonarQube automatizam a coleta e o histórico dessas métricas, permitindo estabelecer **Quality Gates** que bloqueiem merges quando índices de manutenibilidade caem abaixo de limites aceitáveis ([docs.sonarsource.com](https://docs.sonarsource.com/sonarqube-cloud/digging-deeper/metric-definitions/?utm_source=chatgpt.com "Understanding measures and metrics | SonarQube Cloud ...")).

---

## Estudo de Caso: Aplicação Spring Boot analisada com SonarQube

### Contexto

Em um projeto Spring Boot microserviço, realizou-se análise estática com SonarQube versão 10.5 para avaliar a manutenibilidade ([Medium](https://medium.com/%40dulanjayasandaruwan1998/enhancing-code-quality-in-spring-boot-applications-with-sonarqube-a3c2c04e31c1?utm_source=chatgpt.com "Enhancing Code Quality in Spring Boot Applications with SonarQube")).

### O que foi observado

- **Manutenibilidade geral**: rating “B” (média-aceitável).
    
- **Code Smells**: 35 ocorrências classificadas entre Minor e Major.
    
- **Dívida Técnica**: estimada em 10 dias-homem para correção de code smells.
    
- **Cobertura de Testes**: 78 % de linhas, abaixo do alvo de 85 %.
    
- **Complexidade**: média ciclomática de 6 por método, com picos de até 15 em classes de serviço.
    
- **Duplicações**: 3 % de código duplicado, concentrado em utilitários de validação.
    
- **Comentários**: apenas 10 % de linhas comentadas em classes críticas.
    

### Como seria medido

A equipe estabeleceu **Quality Gates**:

- Máximo de 20 code smells.
    
- Dívida técnica inferior a 5 dias-homem.
    
- Cobertura mínima de 85 %.
    

Esses limites foram definidos com base em benchmarks internos e recomendações da ISO/IEC 25023 ([Iteh Standards](https://cdn.standards.iteh.ai/samples/35747/34b91bc957f647ce8bbb2093907d7bc0/ISO-IEC-25023-2016.pdf?utm_source=chatgpt.com "[PDF] INTERNATIONAL STANDARD ISO/IEC 25023")).

### Pontos Fortes

- **Modularidade**: arquitetura em camadas e pacotes bem definidos facilitaram pequenas mudanças.
    
- **Testabilidade**: boa cobertura em camadas de domínio e repositório.
    

### Pontos Fracos

- **Analisabilidade**: falta de comentários em algoritmos complexos prejudica diagnóstico rápido.
    
- **Modificabilidade**: métodos muito longos e alta complexidade ciclomática aumentam o risco de introduzir defeitos.
    
- **Reusabilidade**: duplicação de lógica de validação em múltiplas classes.
    

---

**Conclusão**: a Manutenibilidade, conforme a ISO/IEC 25010, deve ser tratada em todas as fases do ciclo de vida: do design modular à cobertura de testes e documentação adequada. O uso de métricas padronizadas (ISO/IEC 25023) e ferramentas de análise contínua (por exemplo, SonarQube) possibilita monitorar e controlar a saúde da base de código, orientando ações de refatoração e melhoria contínua.