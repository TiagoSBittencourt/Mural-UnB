# Resultados e Entregas da Release Final

Esta seção detalha o estado final do produto **Mural UnB**, consolidando as funcionalidades entregues, as métricas de qualidade alcançadas e as notas de lançamento da versão 1.0.

## Resumo das Entregas

O projeto atingiu seu objetivo principal de centralizar e democratizar o acesso às oportunidades acadêmicas da FGA. A solução final é composta por uma arquitetura desacoplada que garante alta disponibilidade e facilidade de manutenção.

### Principais Entregas Técnicas

1.  **Pipeline de Dados Automatizada (ETL):**
    * Desenvolvimento de scripts em Python robustos para extração de dados de PDFs não estruturados (Editais e Portfólios).
    * Implementação de **Web Crawler** inteligente para busca e download automático de imagens dos laboratórios, com sistema de *fallback* (placeholders categorizados) para garantir a consistência visual.
    
2.  **Enriquecimento com Inteligência Artificial:**
    * Integração com a API do **Google Gemini** para processamento de linguagem natural.
    * Geração automática de *embeddings* e tags semânticas, permitindo um sistema de recomendação e busca muito mais eficiente do que a simples palavra-chave.

3.  **Interface do Usuário (Frontend):**
    * Aplicação React moderna e responsiva, hospedada via GitHub Pages.
    * Design focado na experiência do aluno ("Feed de Oportunidades").

---

## Validação do Escopo Planejado

Abaixo, apresentamos a matriz de rastreabilidade entre o que foi planejado no início do semestre e o que foi efetivamente entregue na Release Final.

| Funcionalidade / Requisito | Status | Detalhes da Entrega |
| :--- | :---: | :--- |
| **Extração de Dados de Laboratórios** | ✅ Entregue | Crawler de PDF + Tratamento de dados via scripts Python. |
| **Extração de Dados de EJs** | ✅ Entregue | Crawler específico para portfólios de Empresas Juniores. |
| **Busca de Imagens Automatizada** | ✅ Entregue | Crawler web com filtros anti-ruído (evita ícones/logos genéricos). |
| **Sistema de Tags Inteligentes** | ✅ Entregue | Uso de LLM para categorizar oportunidades automaticamente. |
| **Interface de Visualização (Feed)** | ✅ Entregue | Frontend React com filtros e busca. |
| **Pipeline de CI/CD** | ✅ Entregue | GitHub Actions configurado para testes e linter. |
| **Cobertura de Testes > 90%** | ✅ Entregue | Suíte de testes unitários com Mocks para o Backend. |

---

## Release Notes (v1.0.0)

### Novas Funcionalidades (Features)

* **Crawler de Imagens Avançado:** Implementação de lógica de "caça" a imagens (Ouro/Prata/Bronze) para encontrar a melhor foto representativa de cada laboratório na web.
* **Smart Fallback:** Sistema que atribui imagens genéricas categorizadas (ex: Software, Energia, Eletrônica) quando nenhuma imagem oficial é encontrada.
* **Embeddings Semânticos:** Geração de vetores matemáticos para descrição dos laboratórios, melhorando a precisão da busca.
* **Extração de PDFs:** Scripts otimizados para leitura dos portfólios oficiais da UnB (Infraestrutura e EJs).

### Qualidade e Infraestrutura

* **Cobertura de Testes Elevada:** Atingimos **~90% de cobertura de código** nos scripts críticos do backend (`extrair_labs_fga.py`, `labs_pdf.py`, pipelines de IA), utilizando `pytest` e `pytest-mock` para isolar dependências externas.
* **Integração Contínua (CI):** Pipeline do GitHub Actions configurada para bloquear PRs que não passem nos testes ou no linter (`pylint`).
* **Refatoração de Código:** Modularização dos scripts Python para permitir testabilidade e manutenção (padrão `if __name__ == "__main__":`).

### Correções de Bugs (Fixes)

* Correção de erro de importação (`urllib`) que impedia o download de certas imagens.
* Ajuste na *blacklist* do crawler para ignorar logos genéricos da UnB, fotos de perfil de professores e grades curriculares.
* Correção na codificação de caracteres ao gerar arquivos JSON para o frontend.

---

## Métricas de Qualidade do Código

Para garantir a sustentabilidade do projeto, adotamos rigorosos padrões de qualidade:

!!! success "Cobertura de Testes"
    Os scripts de backend, responsáveis pela lógica de negócio mais complexa, possuem uma cobertura de testes superior a **89%**, garantindo que alterações futuras não quebrem a extração de dados.

!!! info "Análise Estática"
    O código segue as diretrizes da PEP8, validadas automaticamente pelo **Pylint** com nota superior a **9.0/10**.

---

*Documentação gerada automaticamente para a Release Final do Mural UnB.*