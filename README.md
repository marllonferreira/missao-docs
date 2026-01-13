# missao - Sistema de Gestão de Missões

O **missao** é um sistema web desenvolvido para gerenciar campanhas missionárias, equipes de voluntários e o acompanhamento de interessados. O projeto foca em agilidade, segurança e facilidade de uso para líderes e missionários.

## 🚀 Funcionalidades e Recursos

O sistema **Missão** oferece um conjunto completo de ferramentas para gestão eclesiástica, missões e engajamento, dividido em módulos especializados:

## ⚙️ Estrutura e Modularidade (Campanhas)

O coração do sistema é o conceito de **Campanhas**. Cada evento (ex: "Semana Santa", "Missão Calebe", "Evangelismo Kids") é uma campanha independente.

Ao criar uma campanha, o administrador decide quais recursos ativar, garantindo que o sistema se adapte exatamente à necessidade do momento:
*   ✅ **Modular:** Ative ou desative Gamificação, Leilão, Sorteio e Equipes individualmente.
*   ✅ **Adaptável:** Se uma campanha não precisa de gamificação, os menus e telas relacionados são ocultados automaticamente, mantendo a interface limpa.
*   ✅ **Focado:** Permite gerenciar desde pequenos grupos de estudo até grandes gincanas com centenas de voluntários.

### 📱 Tecnologia & Inovação (PWA)
Desenvolvido com tecnologia **Progressive Web App (PWA)**, o sistema garante uma experiência moderna e resiliente:
*   **Offline-First:** O módulo de visitas funciona perfeitamente sem internet. Os dados são armazenados localmente e sincronizados automaticamente assim que a conexão é restabelecida.
*   **Instalação Nativa:** Pode ser instalado como um aplicativo em dispositivos Android e iOS ou em desktops, sem necessidade de lojas de aplicativos.
*   **Performance:** Interface leve e responsiva, otimizada para uso em campo.

### 🎯 Módulo Missão (Campo)
Focado na experiência do missionário e no trabalho porta a porta, com uma interface pensada para o uso móvel:
*   **Minhas Visitas (App):** Tela exclusiva otimizada para celulares.
    *   **Status Visual:** Identifique rapidamente a situação de cada aluno através de cores (Verde: Visitado hoje / Amarelo: Atrasado / Vermelho: Nunca visitado).
    *   **Gestão de Batismos:** Atualize o status espiritual (Interessado, Agendado, Batizado) diretamente no card do aluno.
    *   **Pontuação Especial:** Lance pontos extras manuais por mérito ou participação em gincanas.
    *   **Histórico Completo:** Acesse o histórico de lições bíblicas, visitas anteriores e pontos acumulados com um toque.
*   **Sincronização Inteligente:** Trabalhe offline o dia todo. O sistema guarda tudo e envia para a nuvem assim que conectar.

### 🏆 Gamificação & Engajamento
Ferramentas visuais poderosas para projetores e telões, desenhadas para animar os eventos:
*   **Placar ao Vivo:** Uma tela *full-screen* dedicada, sem menus ou botões, que exibe o ranking das equipes em tempo real. Ideal para projeção contínua durante o evento.
*   **Leilão de Prêmios:** Sistema interativo onde os participantes usam seus pontos acumulados ("Missão") para dar lances em prêmios reais. Aumenta o engajamento e valoriza a participação.
*   **Sorteio Dinâmico:** Ferramenta visual de sorteio baseada nos presentes ou nas equipes, substituindo papéis manuais por uma experiência digital vibrante.

### 📋 Módulo Secretaria
O coração administrativo da campanha, com controle total sobre dados e pontuação:
*   **Gestão de Equipes:** Criação e organização de equipes, com ferramentas para pontuação coletiva e individual de forma ágil.
*   **Check-in & Check-out:** Registro rápido de presença (manual ou busca inteligente), integrado automaticamente ao sistema de pontuação da equipe.
*   **Distribuição de Alunos:** Funcionalidade para distribuir interessados entre os missionários de forma equilibrada.
*   **Relatórios Avançados:** Geração de relatórios em PDF detalhados sobre produtividade, ranking de equipes e estatísticas de batismo.

### 📊 Relatórios & Inteligência de Dados
O sistema transforma dados em estratégia com uma central completa de Business Intelligence (BI) contendo mais de 15 relatórios:

*   **📈 Batismos & Conversão:**
    *   **Interessados:** Lista de alunos em preparo para o batismo.
    *   **Agendados:** Controle logístico para cerimônias.
    *   **Batizados:** Registro oficial de resultados.
    *   **Funil de Conversão:** Gráfico de eficiência (Interessado ➔ Agendado ➔ Batizado).

*   **👥 Gestão de Alunos:**
    *   **Lista Geral:** Banco de dados completo com filtros por bairro e status.
    *   **Frequência:** Controle de assiduidade e faltas.
    *   **Alunos em Risco (Churn):** Identifica automaticamente alunos propensos a abandonar (baixa frequência/sem visitas).
    *   **Lista de Contatos:** Relatório limpo para ações de telemarketing/WhatsApp.
    *   **Veteranos:** Histórico de fidelidade de participantes recorrentes.
    *   **Histórico de Lições:** Acompanhamento pedagógico do estudo bíblico.

*   **🚀 Performance & Gestão:**
    *   **Evolução Diária:** Gráfico temporal do crescimento da campanha.
    *   **Ranking de Equipes:** Placar detalhado da gincana.
    *   **Desempenho por Missionário:** Produtividade individual (visitas e estudos realizados).
    *   **Pós-Campanha:** Relatório de engajamento para retenção futura.

*   **🛡️ Administrativo:**
    *   **Lista de Colaboradores:** Relação da equipe de trabalho.
    *   **Auditoria Master:** Controle de acessos privilegiados.
    *   **Relatório Geral de Visitas:** Visão macro de visitas realizadas, pendentes e rejeitadas.

### 🛡️ Administrativo & Segurança
Controle robusto para líderes e administradores:
*   **Gestão de Campanhas:** Central de comando para criar metas, acompanhar o progresso global (batismos, estudos) e gerenciar o ciclo de vida das campanhas.
*   **Níveis de Acesso:** Controle granular de permissões (Master, Admin, Secretaria, Visitante).
*   **Backup Simplificado:** Ferramenta de segurança que permite gerar e baixar uma cópia completa do banco de dados com apenas um clique, garantindo a soberania dos seus dados.
*   **Segurança:** Proteção contra ataques comuns (SQL Injection, XSS) e bloqueio automático do instalador após a configuração.

---

## 📦 Manual de Instalação

### Pré-requisitos
*   PHP 8.0 ou superior.
*   Banco de Dados MySQL/MariaDB.
*   Extensões PHP: `pdo`, `pdo_mysql`.
*   Dependências Composer instaladas.

> 📘 **Guia de Instalação Detalhado**
>
> Para instruções completas sobre como preparar o ambiente, instalar dependências (Composer) e realizar a configuração do banco de dados, consulte nosso arquivo dedicado:
>
> 👉 **[Clique aqui para ler o Guia de Instalação (INSTALL.md)](INSTALL.md)**

### Suporte e Propriedade Intelectual

Este é um software proprietário e fechado. Todos os direitos são reservados.
A distribuição não autorizada é proibida.

Copyright (c) 2025-2026 Missão.
