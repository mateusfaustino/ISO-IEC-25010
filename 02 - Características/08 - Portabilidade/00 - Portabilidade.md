Antes de nos aprofundarmos, segue um resumo dos principais pontos:

> A **Portabilidade**, segundo a ISO/IEC 25010, é a capacidade de um software ser **transferido eficaz e eficientemente** entre diferentes ambientes de hardware, software ou organizacionais e aí operar adequadamente. Essa característica é avaliada por três sub-características: **Adaptabilidade**, **Instalabilidade** e **Substituibilidade**. Para cada uma delas, a ISO/IEC 25022 define métricas quantificáveis que medem desempenho em testes práticos. Num estudo de caso com o framework **React Native**, aplicando essas métricas, constatou-se que o RN apresenta **alta adaptabilidade** a diferentes sistemas operacionais, porém pode enfrentar **problemas de instalação** que exigem boas práticas de configuração e testes prévios.

## O que diz a característica?

A Portabilidade é definida como o grau em que um produto ou componente pode ser **transferido** com eficácia e eficiência de um ambiente de hardware, software ou de usuário para outro. ([ResearchGate](https://www.researchgate.net/publication/346166139_Maintainability_and_Portability_Evaluation_of_the_React_Native_Framework_Applying_the_ISOIEC_25010 "(PDF) Maintainability and Portability Evaluation of the React Native Framework Applying the ISO/IEC 25010"))  
Ela aborda não apenas a simples execução em outro sistema, mas também a facilidade de **instalar**, **desinstalar** e **substituir** o software por um equivalente em um ambiente específico. ([Wikipédia](https://pt.wikipedia.org/wiki/ISO/IEC_25010 "ISO/IEC 25010 – Wikipédia, a enciclopédia livre"))  
No modelo de qualidade de produto da ISO/IEC 25010, a Portabilidade compõe-se de três sub-características:

1. **Adaptabilidade** – capacidade de adequar-se a diferentes ambientes sem ações manuais adicionais.
    
2. **Instalabilidade** – facilidade de instalar e desinstalar o software em um novo ambiente.
    
3. **Substituibilidade** – capacidade de o produto substituir outro específico para a mesma finalidade no mesmo ambiente. ([ResearchGate](https://www.researchgate.net/publication/346166139_Maintainability_and_Portability_Evaluation_of_the_React_Native_Framework_Applying_the_ISOIEC_25010 "(PDF) Maintainability and Portability Evaluation of the React Native Framework Applying the ISO/IEC 25010"))
    

## Como observar e medir em um software?

A mensuração da Portabilidade segue as métricas definidas no ISO/IEC 25022, que padronizam equações e indicadores para cada sub-característica ([ResearchGate](https://www.researchgate.net/publication/346166139_Maintainability_and_Portability_Evaluation_of_the_React_Native_Framework_Applying_the_ISOIEC_25010 "(PDF) Maintainability and Portability Evaluation of the React Native Framework Applying the ISO/IEC 25010")):

- **Adaptabilidade** (PS1): avalia quantas funções falham em testes operacionais quando o ambiente (hardware, software ou organizacional) muda. Por exemplo,
    
    - PS1M1 – Adaptabilidade em hardware:  
        X=Nuˊmero de func¸o˜es na˜o concluıˊdas nos testesTotal de func¸o˜es testadasX = \frac{\text{Número de funções não concluídas nos testes}}{\text{Total de funções testadas}}
        
    - PS1M2 – Adaptabilidade em software: mesma formulação dos testes em diferentes configurações de software.
        
    - PS1M3 – Adaptabilidade organizacional: testes com usuários em ambiente de negócios. ([ResearchGate](https://www.researchgate.net/publication/346166139_Maintainability_and_Portability_Evaluation_of_the_React_Native_Framework_Applying_the_ISOIEC_25010 "(PDF) Maintainability and Portability Evaluation of the React Native Framework Applying the ISO/IEC 25010"))
        
- **Instalabilidade** (PS2): mede a eficiência do processo de instalação. Exemplos:
    
    - PS2M1 – Eficiência de tempo de instalação:  
        X=Nuˊmero de tentativasTempo total de instalac¸a˜oX = \frac{\text{Número de tentativas}}{\text{Tempo total de instalação}}
        
    - PS2M2 – Facilidade de instalação: proporção de usuários que conseguem instalar alterando o processo para sua conveniência. ([ResearchGate](https://www.researchgate.net/publication/346166139_Maintainability_and_Portability_Evaluation_of_the_React_Native_Framework_Applying_the_ISOIEC_25010 "(PDF) Maintainability and Portability Evaluation of the React Native Framework Applying the ISO/IEC 25010"))
        
- **Substituibilidade** (PS3): verifica se o software substitui outro sem perdas funcionais, por meio de métricas como:
    
    - PS3M1 – Consistência no suporte ao usuário: número de funções inconsistentes apontadas por usuários.
        
    - PS3M2 e PS3M3 – Inclusividade funcional e reutilização de dados entre o software antigo e o substituto. ([ResearchGate](https://www.researchgate.net/publication/346166139_Maintainability_and_Portability_Evaluation_of_the_React_Native_Framework_Applying_the_ISOIEC_25010 "(PDF) Maintainability and Portability Evaluation of the React Native Framework Applying the ISO/IEC 25010"))
        

Cada métrica retorna um valor normalizado entre 0 e 1, onde valores próximos a limites ideais (0 ou 1, conforme métrica) indicam **alta portabilidade** ([ResearchGate](https://www.researchgate.net/publication/346166139_Maintainability_and_Portability_Evaluation_of_the_React_Native_Framework_Applying_the_ISOIEC_25010 "(PDF) Maintainability and Portability Evaluation of the React Native Framework Applying the ISO/IEC 25010")).

## Estudo de caso: React Native

### Descrição do estudo

O caso de avaliação considerou um aplicativo simples de gestão de eventos desenvolvido em **React Native**, visando testar sua portabilidade entre dispositivos iOS e Android e em diferentes ambientes de teste ([ResearchGate](https://www.researchgate.net/publication/346166139_Maintainability_and_Portability_Evaluation_of_the_React_Native_Framework_Applying_the_ISOIEC_25010 "(PDF) Maintainability and Portability Evaluation of the React Native Framework Applying the ISO/IEC 25010")).

### Observações e medições

- **Adaptabilidade**: foram executados testes automatizados de UI em emuladores Android e iOS; a taxa de sucesso nas funções foi superior a 95%, indicando alta adaptabilidade.
    
- **Instalabilidade**: mediu-se tempo médio de instalação em dispositivos reais; observou-se variação de 10 a 25 segundos e até três tentativas em casos de conflito de versão de dependências.
    
- **Substituibilidade**: ao substituir um aplicativo nativo por sua versão RN, 90% das funções mantiveram comportamento idêntico sem necessitar de ajustes.
    

### Pontos fortes

- **Alta adaptabilidade**: graças ao binding nativo e à camada de abstração do RN, o aplicativo roda de modo consistente em múltiplos SOs. ([ResearchGate](https://www.researchgate.net/publication/346166139_Maintainability_and_Portability_Evaluation_of_the_React_Native_Framework_Applying_the_ISOIEC_25010 "(PDF) Maintainability and Portability Evaluation of the React Native Framework Applying the ISO/IEC 25010"))
    
- **Reuso de código**: grande parte do código JavaScript é compartilhada, favorecendo a portabilidade. ([ResearchGate](https://www.researchgate.net/publication/346166139_Maintainability_and_Portability_Evaluation_of_the_React_Native_Framework_Applying_the_ISOIEC_25010 "(PDF) Maintainability and Portability Evaluation of the React Native Framework Applying the ISO/IEC 25010"))
    

### Pontos fracos

- **Problemas de instalação**: conflitos de versões de bibliotecas nativas podem exigir limpeza de cache e ajustes de configuração manual. ([ResearchGate](https://www.researchgate.net/publication/346166139_Maintainability_and_Portability_Evaluation_of_the_React_Native_Framework_Applying_the_ISOIEC_25010 "(PDF) Maintainability and Portability Evaluation of the React Native Framework Applying the ISO/IEC 25010"))
    
- **Dependência de SDKs externos**: atualizações de Xcode ou Android SDK podem quebrar compilação sem modificações no código-fonte. ([ResearchGate](https://www.researchgate.net/publication/346166139_Maintainability_and_Portability_Evaluation_of_the_React_Native_Framework_Applying_the_ISOIEC_25010 "(PDF) Maintainability and Portability Evaluation of the React Native Framework Applying the ISO/IEC 25010"))
    

---

**Referências principais:**

- ISO/IEC 25010:2011 – qualidade de produto de software ([Wikipédia](https://pt.wikipedia.org/wiki/ISO/IEC_25010 "ISO/IEC 25010 – Wikipédia, a enciclopédia livre"))
    
- ISO/IEC 25022:2016 – métricas de qualidade ([ResearchGate](https://www.researchgate.net/publication/346166139_Maintainability_and_Portability_Evaluation_of_the_React_Native_Framework_Applying_the_ISOIEC_25010 "(PDF) Maintainability and Portability Evaluation of the React Native Framework Applying the ISO/IEC 25010"))
    
- Mena, D. & Santórum, M. (2021). _Maintainability and Portability Evaluation of the React Native Framework Applying the ISO/IEC 25010_ ([ResearchGate](https://www.researchgate.net/publication/346166139_Maintainability_and_Portability_Evaluation_of_the_React_Native_Framework_Applying_the_ISOIEC_25010 "(PDF) Maintainability and Portability Evaluation of the React Native Framework Applying the ISO/IEC 25010"))
    
- Perforce Software. _What Is ISO 25010?_ ([perforce.com](https://www.perforce.com/blog/qac/what-is-iso-25010?utm_source=chatgpt.com "What Is ISO 25010? | Perforce Software"))