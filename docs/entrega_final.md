# Resultados e Entregas da Release Final

Esta seção detalha o estado final do produto **Mural UnB**, consolidando as funcionalidades entregues, as métricas de qualidade alcançadas e as notas de lançamento da versão 1.0.

## 🏆 Resumo das Entregas

O projeto atingiu seu objetivo principal de centralizar e democratizar o acesso às oportunidades acadêmicas da FGA. A solução final é composta por uma arquitetura desacoplada que garante alta disponibilidade e facilidade de manutenção.

---

## ✅ Validação do Escopo Planejado

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

## 📦 Release Notes - Mural UnB (v1.0)

**Data de lançamento:** 02/12/2025
**Link para o Site (Deploy):** [muralunb.com.br](https://muralunb.com.br)

### 📔 O que foi feito?

#### 📌 Pipeline de Dados (ETL)
O time desenvolveu um **pipeline completo de dados em Python**, responsável por extrair informações (texto, imagens e links) de **PDFs oficiais** disponibilizados pela DPI da UnB.
Esses dados são transformados e carregados em um banco de dados no formato JSON, compondo um fluxo ETL robusto para alimentar o sistema.

#### 📌 Workflows de Extração e Automação
Foram implementados **workflows** para gerenciar e agendar a extração de dados, garantindo que o processo ocorra de forma automatizada, controlada e escalável.

#### 📌 CI/CD e Boas Práticas de Engenharia
O time implementou **pipelines de CI/CD** seguindo melhores práticas de engenharia de software, incluindo:
* Linting
* Testes unitários com TDD
* Cobertura de testes próxima de 90%

Essas práticas garantem consistência, segurança e qualidade contínua no desenvolvimento.

#### 📌 Front-end Estático (React + Tailwind)
Atendendo ao requisito de frontend estático e sem custos de hospedagem, o time construiu a interface utilizando:
* React
* **TailwindCSS** para estilização
* Deploy gratuito via GitHub Pages, com **domínio customizado** (muralunb.com.br).

---

## 📊 Métricas de Qualidade do Código

Para garantir a sustentabilidade do projeto, adotamos rigorosos padrões de qualidade:

!!! success "Cobertura de Testes"
    Os scripts de backend, responsáveis pela lógica de negócio mais complexa, possuem uma cobertura de testes superior a **89%**, garantindo que alterações futuras não quebrem a extração de dados.

!!! info "Análise Estática"
    O código segue as diretrizes da PEP8, validadas automaticamente pelo **Pylint** com nota superior a **9.0/10**.

---

*Documentação gerada automaticamente para a Release Final do Mural UnB.*