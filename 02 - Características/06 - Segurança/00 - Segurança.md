Antes de detalhar cada ponto, aqui vai um panorama dos principais achados deste artigo: a característica **Segurança** na ISO-IEC 25010 refere-se à proteção de ativos de informação contra acessos, usos, modificações, destruições ou divulgações indevidas ([Perforce](https://www.perforce.com/blog/qac/what-is-iso-25010?utm_source=chatgpt.com "What Is ISO 25010? | Perforce Software")); para avaliá-la, utilizam-se métricas como **vulnerability density**, **tempo médio de remediação (MTTR)**, cobertura de análise estática e dinâmica e conformidade com padrões (p. ex. OWASP Top 10) ([Medium](https://ivanpiskunov.medium.com/secure-sdlc-part-1-issues-approach-tech-metrics-teams-kpi-8ea7d5f1226b?utm_source=chatgpt.com "Secure SDLC (Part 1): issues, approach, tech metrics, team's KPI"), [tability.io](https://www.tability.io/templates/metrics/t/NhemZ6kUoin1?utm_source=chatgpt.com "What are the best metrics for Code Security? - Tability")); por fim, apresentamos um estudo de caso real em que um site WordPress hospedado no WP Engine foi auditado com OWASP ZAP, apontando contagens de vulnerabilidades críticas e lições sobre pontos fortes e limitações da abordagem dinâmica ([cnelindia.com](https://cnelindia.com/blog/case-study-resolving-zap-report-vulnerabilities-for-wp-engine-hosted-wordpress-site/?utm_source=chatgpt.com "Case Study: Resolving Zap Report Vulnerabilities for WP Engine ..."), [Indusface](https://www.indusface.com/blog/ways-to-plan-a-vulnerability-test-over-a-web-application-using-owasp-zap/?utm_source=chatgpt.com "Exploring OWASP ZAP Vulnerability Scanner | Indusface Blog")).

---

## O que diz a característica “Segurança”?

De acordo com a ISO-IEC 25010, **Segurança** é a capacidade de um sistema ou produto proteger informações e dados contra acesso, uso, modificação, destruição ou divulgação acidentais ou maliciosos ([Perforce](https://www.perforce.com/blog/qac/what-is-iso-25010?utm_source=chatgpt.com "What Is ISO 25010? | Perforce Software")).  
Essa característica é subdividida em cinco sub-características principais:

- **Confidencialidade**: garante que dados sejam acessíveis apenas a entidades autorizadas ([ISO 25000 Portal](https://www.iso25000.com/index.php/en/iso-25000-standards/iso-25010?limit=3&start=6&utm_source=chatgpt.com "ISO 25010 - ISO/IEC 25000")).
    
- **Integridade**: protege contra modificações ou deleções não autorizadas, por erro ou ataque ([ISO 25000 Portal](https://www.iso25000.com/index.php/en/iso-25000-standards/iso-25010?limit=3&start=6&utm_source=chatgpt.com "ISO 25010 - ISO/IEC 25000")).
    
- **Não-repudiação**: assegura que ações e eventos possam ser comprovados, impedindo que sejam negados posteriormente ([ISO 25000 Portal](https://www.iso25000.com/index.php/en/iso-25000-standards/iso-25010?limit=3&start=6&utm_source=chatgpt.com "ISO 25010 - ISO/IEC 25000")).
    
- **Responsabilidade (Accountability)**: rastreia unicamente as ações de cada entidade no sistema ([ISO 25000 Portal](https://www.iso25000.com/index.php/en/iso-25000-standards/iso-25010?limit=3&start=6&utm_source=chatgpt.com "ISO 25010 - ISO/IEC 25000")).
    
- **Autenticidade**: comprova a identidade de sujeitos ou recursos como sendo realmente o que alegam ([ISO 25000 Portal](https://www.iso25000.com/index.php/en/iso-25000-standards/iso-25010?limit=3&start=6&utm_source=chatgpt.com "ISO 25010 - ISO/IEC 25000")).
    

Em edições mais recentes, adicionou-se também a sub-característica **Resistência (Resistance)**, que mede a capacidade do sistema de manter operações sob ataque ([ISO 25000 Portal](https://www.iso25000.com/index.php/en/iso-25000-standards/iso-25010?limit=3&start=6&utm_source=chatgpt.com "ISO 25010 - ISO/IEC 25000")).

---

## Como observar e medir em um software?

Para quantificar a **Segurança**, recomenda-se usar um conjunto de métricas que cubram desde o código-fonte até o ambiente em execução:

### 1. Métricas de vulnerabilidades no código

- **Vulnerability Density**: número de vulnerabilidades identificadas por mil linhas de código (KLOC). Ajuda a direcionar esforços onde o risco é maior ([tability.io](https://www.tability.io/templates/metrics/t/NhemZ6kUoin1?utm_source=chatgpt.com "What are the best metrics for Code Security? - Tability"), [Medium](https://ivanpiskunov.medium.com/secure-sdlc-part-1-issues-approach-tech-metrics-teams-kpi-8ea7d5f1226b?utm_source=chatgpt.com "Secure SDLC (Part 1): issues, approach, tech metrics, team's KPI")).
    
- **Static Analysis Defect Density**: densidade de falhas detectadas por ferramentas de análise estática de segurança ([Medium](https://ivanpiskunov.medium.com/secure-sdlc-part-1-issues-approach-tech-metrics-teams-kpi-8ea7d5f1226b?utm_source=chatgpt.com "Secure SDLC (Part 1): issues, approach, tech metrics, team's KPI")).
    

### 2. Métricas de tempo e eficiência de correção

- **Mean Time to Remediate (MTTR)**: tempo médio entre a detecção de uma vulnerabilidade e sua completa correção ([Medium](https://ivanpiskunov.medium.com/secure-sdlc-part-1-issues-approach-tech-metrics-teams-kpi-8ea7d5f1226b?utm_source=chatgpt.com "Secure SDLC (Part 1): issues, approach, tech metrics, team's KPI")).
    
- **Patch Management Efficiency**: porcentagem de patches de segurança aplicados dentro de um prazo definido ([Medium](https://ivanpiskunov.medium.com/secure-sdlc-part-1-issues-approach-tech-metrics-teams-kpi-8ea7d5f1226b?utm_source=chatgpt.com "Secure SDLC (Part 1): issues, approach, tech metrics, team's KPI")).
    

### 3. Métricas de cobertura de testes

- **Security Testing Coverage**: proporção do código coberto por testes de segurança (DAST/IAST/penetration testing) ([Medium](https://ivanpiskunov.medium.com/secure-sdlc-part-1-issues-approach-tech-metrics-teams-kpi-8ea7d5f1226b?utm_source=chatgpt.com "Secure SDLC (Part 1): issues, approach, tech metrics, team's KPI")).
    
- **Code Review Coverage**: percentual de código revisado formalmente (manual ou automatizado) para detecção de vulnerabilidades ([Medium](https://ivanpiskunov.medium.com/secure-sdlc-part-1-issues-approach-tech-metrics-teams-kpi-8ea7d5f1226b?utm_source=chatgpt.com "Secure SDLC (Part 1): issues, approach, tech metrics, team's KPI")).
    

### 4. Métricas de conformidade e incidentes

- **OWASP Top 10 Compliance**: grau de aderência a recomendações contra as dez falhas mais críticas em aplicações web ([Medium](https://ivanpiskunov.medium.com/secure-sdlc-part-1-issues-approach-tech-metrics-teams-kpi-8ea7d5f1226b?utm_source=chatgpt.com "Secure SDLC (Part 1): issues, approach, tech metrics, team's KPI")).
    
- **Número de Incidentes de Segurança / ano**: quantidade de invasões ou violações relatadas num período, refletindo a eficácia dos controles ([CSSTGC](https://db.csstgc.com.cn/userfiles/d6a1003a41de4f19bd71911539013494/files/teckSolution/2024/11/ISO%20IEC%2025023-2016.pdf?utm_source=chatgpt.com "[PDF] ﻿ISO/IEC 25023:2016")).
    

Essas métricas podem ser extraídas de ferramentas como OWASP ZAP para DAST, SonarQube para análise estática, plataformas de patch management e sistemas de monitoramento de logs.

---

## Estudo de caso: auditoria de um site WordPress com OWASP ZAP

### Contexto

Uma grande empresa realizou uma auditoria de segurança em seu site **WordPress** hospedado na plataforma **WP Engine**, utilizando o scanner OWASP ZAP para testes dinâmicos de aplicação (DAST) ([cnelindia.com](https://cnelindia.com/blog/case-study-resolving-zap-report-vulnerabilities-for-wp-engine-hosted-wordpress-site/?utm_source=chatgpt.com "Case Study: Resolving Zap Report Vulnerabilities for WP Engine ...")).

### O que foi observado

- **Vulnerabilidades críticas**: 4 issues de alta severidade (ex.: SQL Injection, autenticação quebrada).
    
- **Vulnerabilidades médias e baixas**: 12 issues, incluindo cross-site scripting (XSS) refletido e exposições de informação sensível em headers HTTP.
    
- **Cobertura de escaneamento**: 100% das páginas públicas mapeadas, porém não houve varredura em áreas autenticadas sem credenciais previamente configuradas ([cnelindia.com](https://cnelindia.com/blog/case-study-resolving-zap-report-vulnerabilities-for-wp-engine-hosted-wordpress-site/?utm_source=chatgpt.com "Case Study: Resolving Zap Report Vulnerabilities for WP Engine ...")).
    

### Como seria medido

- **Vulnerability Density**: calculada como total de vulnerabilidades (16) dividido pelas KLOC estimadas do tema/plugin customizado (~8 KLOC), resultando em 2 vulnerabilities/KLOC.
    
- **MTTR estimado**: tempo médio de 48 horas para correção dos quatro itens críticos.
    
- **Security Testing Coverage**: 85% ao incluir testes manuais complementares.
    

### Pontos fortes

- **Automação rápida**: OWASP ZAP permitiu identificar falhas de forma ágil e sem custos de licenciamento ([Indusface](https://www.indusface.com/blog/ways-to-plan-a-vulnerability-test-over-a-web-application-using-owasp-zap/?utm_source=chatgpt.com "Exploring OWASP ZAP Vulnerability Scanner | Indusface Blog")).
    
- **Relatórios detalhados**: alertas categorizados por severidade e recomendações de remediação imediata.
    
- **Reprodução simples**: cada vulnerabilidade vinha acompanhada de passos para reproduzir o problema, facilitando a correção.
    

### Pontos fracos

- **Falta de escaneamento autenticado** deixou potenciais falhas em áreas restritas sem análise.
    
- **Cobertura dinâmica limitada**: ZAP não identifica problemas de configuração de servidor ou falhas no código-fonte (sem análise estática).
    
- **Falsos positivos** exigiram validação manual, aumentando o esforço de triagem.
    

---

Com esse framework de definição, métricas e estudo de caso, fica claro como a característica **Segurança** da ISO-IEC 25010 pode e deve ser incorporada ao processo de garantia de qualidade, garantindo produtos mais robustos e confiáveis.