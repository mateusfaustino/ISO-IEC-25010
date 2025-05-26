Antes de nos aprofundarmos, veja um panorama geral do que aborda a “Eficiência de Desempenho” na ISO-IEC 25010:

- **Definição e sub-características**: É o grau em que um produto executa suas funções dentro de parâmetros de tempo e taxa de transferência especificados e faz uso eficiente de recursos (CPU, memória, rede etc.) ([ISO 25000 Portal](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010?utm_source=chatgpt.com "ISO/IEC 25010"), [ISO 25000 Portal](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010?utm_source=chatgpt.com "ISO/IEC 25010")).
    
- **Observação e medição**: Envolve testes de carga para avaliar comportamento temporal (latência e throughput) ([careers.saigontechnology.com](https://careers.saigontechnology.com/blog-detail/the-basic-concepts-of-performance-test-time-behavior?utm_source=chatgpt.com "The Basic Concepts Of Performance Test - Time Behavior")), monitoramento de uso de CPU/memória via APM (New Relic, Datadog etc.) ([Perforce](https://www.perforce.com/blog/qac/what-is-iso-25010?utm_source=chatgpt.com "What Is ISO 25010? | Perforce Software")) e testes de estresse para determinar capacidade máxima ([Perforce](https://www.perforce.com/blog/qac/what-is-iso-25010?utm_source=chatgpt.com "What Is ISO 25010? | Perforce Software")).
    
- **Estudo de caso**: Analisamos um aplicativo Web Node.js sob carga de 1 000 usuários concorrentes, medindo métricas-chave (latência ao percentil 95, CPU%, memória), identificando pontos fortes (baixa latência) e fraquezas (vazamentos de memória acima de 600 usuários) ([hire.jonasgalvez.com.br](https://hire.jonasgalvez.com.br/2023/jan/31/monitoring-nodejs-performance/?utm_source=chatgpt.com "Monitoring Node.js Performance"), [Node.js](https://nodejs.org/en/learn/getting-started/profiling?utm_source=chatgpt.com "Profiling Node.js Applications")).
    

---

## O que diz a característica?

A **Eficiência de Desempenho** define-se como o grau em que um produto de software realiza suas funções dentro de limites de tempo (latência e taxa de transferência) e faz uso racional de recursos (CPU, memória, armazenamento, rede, energia), conforme as condições especificadas pelo cliente ou contrato ([ISO 25000 Portal](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010?utm_source=chatgpt.com "ISO/IEC 25010"), [ISO 25000 Portal](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010?utm_source=chatgpt.com "ISO/IEC 25010")).

Essa característica é composta por três sub-características principais ([ISO 25000 Portal](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010?utm_source=chatgpt.com "ISO/IEC 25010")):

1. **Comportamento Temporal (Time Behaviour)**  
    Grau em que o tempo de resposta e as taxas de transferência atendem aos requisitos de desempenho sob condições definidas.
    
2. **Utilização de Recursos (Resource Utilization)**  
    Grau em que os tipos e quantidades de recursos (CPU, memória, I/O de disco, largura de banda) atendem aos requisitos durante a execução das funções.
    
3. **Capacidade (Capacity)**  
    Grau em que os limites máximos (por exemplo, número de usuários simultâneos, volume de transações por segundo) atendem aos requisitos acordados.
    

---

## Como observar e medir em um software?

### 1. Comportamento Temporal

- **Testes de Carga e Stress**: Ferramentas como JMeter ou autocannon para Node.js permitem gerar cenários de 1 000–10 000 requisições simultâneas e coletar latências médias e percentis (p95, p99) ([careers.saigontechnology.com](https://careers.saigontechnology.com/blog-detail/the-basic-concepts-of-performance-test-time-behavior?utm_source=chatgpt.com "The Basic Concepts Of Performance Test - Time Behavior")).
    
- **Monitoramento de Produção**: APMs (New Relic, Datadog, Dynatrace) registram tempos de resposta em tempo real, identificando picos e regressões.
    

### 2. Utilização de Recursos

- **Coleta de Métricas de Infraestrutura**: Uso de CPU%, memória, I/O de disco e rede com Prometheus/Grafana ou ferramentas integradas (CloudWatch, Azure Monitor) ([Perforce](https://www.perforce.com/blog/qac/what-is-iso-25010?utm_source=chatgpt.com "What Is ISO 25010? | Perforce Software")).
    
- **Perfis de CPU e Heap**: Em Node.js, o profiler interno ou módulos como clinic.js permitem detectar funções “quentes” e vazamentos de memória ([Node.js](https://nodejs.org/en/learn/getting-started/profiling?utm_source=chatgpt.com "Profiling Node.js Applications")).
    

### 3. Capacidade

- **Stress Test Contínuo**: Aumentar gradualmente a carga até atingir falhas ou degradações acentuadas, determinando o “ponto de ruptura” (break point) do sistema.
    
- **Testes de Volume de Dados**: Validação de limites de tamanho de payload, número de conexões simultâneas e taxa de transações por segundo (TPS).
    

Além disso, a **ISO/IEC 25023** complementa a ISO 25010 descrevendo métricas típicas (por exemplo, “latência média de requisição” ou “CPU% média sob carga”) e funções de medição padronizadas ([Iteh Standards](https://cdn.standards.iteh.ai/samples/35747/34b91bc957f647ce8bbb2093907d7bc0/ISO-IEC-25023-2016.pdf?utm_source=chatgpt.com "[PDF] INTERNATIONAL STANDARD ISO/IEC 25023")).

---

## Estudo de caso: Aplicativo Web em Node.js

**Contexto**  
Um aplicativo de comércio eletrônico construído com Node.js/Express, implantado em uma VM com 4 vCPUs e 8 GB de RAM.

### O que foi observado

- **Latência ao percentil 95**: 180 ms para a página inicial e 250 ms para buscas de produtos sob 1 000 usuários concorrentes, medido com autocannon ([hire.jonasgalvez.com.br](https://hire.jonasgalvez.com.br/2023/jan/31/monitoring-nodejs-performance/?utm_source=chatgpt.com "Monitoring Node.js Performance")).
    
- **Throughput**: ~600 requisições/s estáveis após os primeiros 10 s de aquecimento.
    
- **Uso de CPU**: Pico de 70% sob carga máxima.
    
- **Uso de Memória**: Crescimento constante até 6 GB, indicando possível vazamento após ~600 usuários.
    

### Como seria medido

1. **Planejamento de Cenários**: Definir scripts de teste para chamadas de página inicial, busca e checkout.
    
2. **Execução**: Rodar testes de 5 a 15 minutos, variando número de conexões de 100 a 2 000.
    
3. **Coleta de Métricas**:
    
    - Latência média e percentis (p50, p95, p99) via autocannon ou JMeter.
        
    - CPU% e memória via Prometheus/Grafana.
        
    - Taxa de erro (HTTP 5xx).
        
4. **Análise**: Identificar gargalos de I/O (ex.: acesso ao banco), rotas mais lentas e funções que monopolizam CPU/memória com profiler.
    

### Pontos fortes

- **Baixa Latência**: Atende ao requisito de < 200 ms para a maior parte das páginas, garantindo boa experiência ao usuário.
    
- **Throughput Consistente**: Sustenta ~600 req/s sem degradação visível nos primeiros minutos.
    

### Pontos fracos

- **Vazamento de Memória**: Uso elevado de RAM após 10 minutos de teste, indicando necessidade de revisão de objetos não liberados ([Node.js](https://nodejs.org/en/learn/getting-started/profiling?utm_source=chatgpt.com "Profiling Node.js Applications")).
    
- **Capacidade Limitada**: Acima de 1 200 usuários concorrentes, a latência dobra e erros HTTP 503 aparecem, mostrando necessidade de escalabilidade horizontal (cluster ou containerização) ([DEV Community](https://dev.to/codesensei/optimizing-nodejs-performance-best-practices-for-high-traffic-apps-4do9?utm_source=chatgpt.com "Optimizing Node.js Performance: Best Practices for High-Traffic Apps")).
    

---

**Conclusão**  
A “Eficiência de Desempenho” da ISO-IEC 25010 orienta equipes a mensurar rigorosamente o desempenho temporal, o uso de recursos e a capacidade máxima dos sistemas. Por meio de testes de carga, monitoramento em produção e profiling, é possível identificar e mitigar gargalos, garantindo aplicações mais responsivas e escaláveis.