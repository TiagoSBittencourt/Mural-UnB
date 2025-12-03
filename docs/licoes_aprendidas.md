# Lições Aprendidas

Esta seção documenta a retrospectiva da equipe ao final do projeto, destacando sucessos, desafios e o crescimento técnico e profissional adquirido durante o desenvolvimento do Mural UnB.

## O que funcionou bem

* **Automação de Processos:** A decisão de investir tempo na criação de *scripts* de *web scraping* e processamento de dados provou-se eficaz. Automatizar a coleta de informações dos editais e sites da UnB garantiu que a base de dados se mantivesse atualizada sem intervenção manual constante.
* **Integração com IA:** O uso da API do Google Gemini para gerar *embeddings* e categorizar laboratórios superou as expectativas. A solução permitiu criar um sistema de busca semântica e filtros inteligentes que seriam complexos de implementar com algoritmos tradicionais.
* **Qualidade de Código (CI/CD):** A implementação precoce de *pipelines* de Integração Contínua (GitHub Actions) com testes unitários e *linters* elevou o padrão do código. Isso preveniu regressões e facilitou a revisão de *Pull Requests*, mantendo a *branch* principal estável.
* **Comunicação Assíncrona:** A equipe conseguiu manter um fluxo de trabalho produtivo utilizando *issues* bem descritas e documentação no GitHub, o que reduziu a dependência de reuniões síncronas longas.

## O que poderia ter sido melhor

* **Curva de Aprendizado do Frontend:** Inicialmente, houve desafios na adaptação ao ecossistema React/Vite para alguns membros, o que gerou um gargalo no desenvolvimento da interface nas primeiras *sprints*. Um pareamento (*pair programming*) mais intenso no início poderia ter mitigado essa dificuldade.
* **Gerenciamento de Dependências:** A complexidade das bibliotecas Python (como `pdfplumber` e `fitz`) causou conflitos em ambientes diferentes (Windows vs. Linux). A padronização via Docker desde o início teria evitado problemas de configuração local.
* **Definição de Escopo Inicial:** Algumas funcionalidades planejadas (como o sistema de notificação por e-mail) tiveram que ser movidas para versões futuras devido à subestimação do tempo necessário para refinar a extração de dados dos PDFs não estruturados.

## Ajustes feitos ao longo do projeto

* **Refatoração dos Scripts:** Percebemos que os *scripts* de extração estavam muito acoplados e difíceis de testar. Realizamos uma refatoração significativa para modularizar o código (padrão `if __name__ == "__main__":`), permitindo a criação de testes unitários isolados.
* **Estratégia de Imagens:** A ideia original de usar apenas logotipos dos laboratórios mostrou-se visualmente pobre. Ajustamos o *crawler* para buscar imagens reais nos sites e implementamos um sistema de *fallback* com *placeholders* temáticos (ex: Software, Energia) para garantir uma interface visualmente agradável mesmo quando a busca falha.
* **Fluxo de Git:** Ajustamos a política de *branches* para exigir *reviews* obrigatórios e aprovação nos testes automáticos antes do *merge*, o que reduziu drasticamente a incidência de *bugs* na versão de produção.

## Impacto da experiência

O desenvolvimento do Mural UnB proporcionou um ambiente prático para aplicar conceitos de Engenharia de Software em um problema real.

* **Técnico:** A equipe consolidou conhecimentos em Python avançado, manipulação de dados não estruturados, consumo de APIs de IA Generativa e construção de *interfaces* modernas com React.
* **Processual:** A vivência com metodologias ágeis, controle de versão rigoroso e documentação técnica reforçou a importância da organização e da qualidade de software acima da simples entrega de código funcional.
* **Profissional:** A necessidade de resolver problemas complexos de dados e entregar valor para a comunidade acadêmica fortaleceu a capacidade de análise crítica e trabalho colaborativo dos membros.