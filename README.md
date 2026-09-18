# ÂMBRA — Análise e Mapeamento da Biodiversidade e Relações Ambientais

> Plataforma integrada de exploração científica, modelagem de ecossistemas e análise relacional da biodiversidade terrestre e paleobiológica.

---

## 📌 Visão Geral

O **ÂMBRA** (Análise e Mapeamento da Biodiversidade e Relações Ambientais) é uma plataforma web projetada para centralizar, correlacionar e contextualizar dados sobre espécies contemporâneas e extintas em um ambiente digital dinâmico, visual e educativo.

Mais do que uma enciclopédia taxonômica convencional, o ÂMBRA transforma dados biológicos dispersos em uma experiência relacional: conecta espécimes a seus respectivos períodos geológicos, biomas continentais ou marinhos e teias ecológicas (predação, competição e simbiose). 

A proposta central é unir o rigor formal dos dados científicos de biodiversidade a uma arquitetura de navegação interativa, orientada pela descoberta de ecossistemas e visualização de redes ecológicas.

---

## 🎯 Objetivos do Sistema

- **Centralização Científica:** Reunir registros de taxonomia, ocorrências fósseis e dados morfológicos de bases científicas abertas.
- **Contextualização Contínua:** Impedir que registros biológicos existam de forma isolada; cada espécie é rigidamente amarrada ao seu recorte cronológico e ambiental.
- **Mapeamento de Relações Ecológicas:** Representar interações biológicas interespecíficas por meio de modelos estruturados e grafos visuais.
- **Geração de Ecossistemas:** Permitir ao usuário recriar e inspecionar cenários ambientais coerentes a partir de combinações espaciais e temporais.
- **Disseminação Científica:** Fornecer interfaces intuitivas e confiáveis para estudantes, pesquisadores, educadores e entusiastas da história da vida na Terra.

---

## 🏛️ Pilares Fundamentais

1. **Exploração Não-Linear:** Cada página ou espécime funciona como um ponto de entrada para conexões maiores (gênero, família, bioma de ocorrência, predadores e presas).
2. **Rigor e Integridade de Dados:** Validação estrita de cronologias temporais (eras e períodos em Ma) e integridade hierárquica taxonômica completa (Reino, Filo, Classe, Ordem, Família e Gênero).
3. **Descoberta Contextual:** Sugestões e correlações baseadas em afinidade evolutiva, espacial ou trófica.
4. **Educação Visual:** Substituição de listas densas e estáticas por matrizes relacionais e grafos interativos de teias alimentares.

---

## ⚙️ Módulos e Funcionalidades

### 1. Enciclopédia Taxonômica e Catálogo
- Pesquisa global por nome científico ou nomes populares com auto-complete.
- Ficha detalhada por espécie: taxonomia padronizada, dimensões corporais estimadas, hábitos alimentares (dieta) e sumário científico.
- Catálogos dedicados para Períodos Geológicos (com ordenação cronológica) e Biomas terrestres/aquáticos.
- Módulo *Explore Mais*: recomendação dinâmica baseada em proximidade taxonômica e nicho ecológico.

### 2. Motor de Ecossistemas
- **Filtro Cruzado:** Seleção combinada de Período Geológico e Bioma para montagem precisa do habitat.
- **Teias e Cadeias Tróficas:** Renderização visual de interações ecológicas diretas entre os organismos presentes no recorte.
- **Modo Veracidade vs. Modo Hipotético ("What If"):** 
  - *Veracidade:* Exibe apenas relações diretas cientificamente documentadas.
  - *What If:* Simulação lógica em tempo real calculando compatibilidades de predação e disputa territorial com base em portes físicos e dietas dos espécimes.

### 3. Pipeline Automatizado de Ingestão de Dados (ETL)
- **Extração:** Conexão com serviços de dados globais e bases abertas (PBDB, GBIF, WoRMS, PhyloPic).
- **Transformação:** Higienização de payloads, conformidade taxonômica via schemas tipados e tratamento de inconsistências de idade geológica.
- **Carga:** Persistência relacional protegida contra duplicidade por chave científica única.

### 4. Coleções e Gestão de Usuários
- Perfis de acesso: *Visitante*, *Usuário Registrado* e *Administrador*.
- Curadoria do acervo com salvamento de espécies em listas personalizadas.
- Painel de curadoria científica para cadastro, auditoria de integridade e gestão do acervo.

---

## 🛠️ Arquitetura e Tecnologias

O sistema é construído sob uma arquitetura desacoplada cliente-servidor, orientada a padrões de alta coesão e tipagem estática ponta a ponta:

```text
               ┌──────────────────────────────┐
               │    Front-End (React/Vite)    │
               │   Tailwind CSS + Data Viz    │
               └──────────────┬───────────────┘
                              │ HTTP / REST
               ┌──────────────▼───────────────┐
               │     Back-End (Node/Express)  │
               │  TypeScript • Camada Service │
               └──────┬───────────────────────┘
                      │
        ┌─────────────┴─────────────┐
        │ Prisma ORM                │ Pipeline de Ingestão (ETL)
        │ PostgreSQL                │ [PBDB / GBIF / PhyloPic]
        └───────────────────────────┘
```

- **Linguagem Base:** TypeScript (Front-end e Back-end).
- **Front-end:** React, Vite, Tailwind CSS, Axios, React Router.
- **Back-end:** Node.js, Express, Zod (validação de schemas e regras de entrada).
- **Banco de Dados & ORM:** PostgreSQL com Prisma ORM.
- **Infraestrutura:** Docker e Docker Compose para orquestração de containers.

---

## 📜 Licença

Este projeto possui direitos autorais reservados. Disponível apenas para consulta e avaliação técnica.
