📊 UNIFEI/SDI - Dashboard de Gestão Acadêmica e Pesquisa

Painel interativo em Power BI desenvolvido para centralização, tratamento e análise de indicadores das diretrizes de Ensino, Pesquisa e Extensão da Universidade Federal de Itajubá (UNIFEI). O projeto foi construído focando em usabilidade executiva, precisão de dados e padronização visual.
Objetivos do Projeto

    Consolidação de Dados: Integrar dados provenientes de 5 bases CSV distintas.

    Tratamento de Dados (ETL): Corrigir inconsistências estruturais, como problemas graves de codificação de texto (mojibake) e registros duplicados.

    Visualização Executiva: Prover à gestão (SDI/UNIFEI) uma interface intuitiva com visualização rápida de KPIs e relatórios detalhados.

Desafios Técnicos & Soluções Aplicadas

1. Tratamento Avançado de Codificação (Mojibake)

    Problema: Bases legadas de sistemas acadêmicos apresentavam caracteres corrompidos em acentuações devido ao choque entre padrões ISO 8859-1 (Latin-1), Windows-1252 e UTF-8.

    Solução: Reinterpretação de bytes no Power Query utilizando fórmulas customizadas em M para restauração de encodings corrompidos:
    Code snippet

    Text.FromBinary(Text.ToBinary([Nome do Campo], 1252), TextEncoding.Utf8)

2. Deduplicação e Integridade Granular

    Problema: Registros duplicados decorrentes de inconsistências de extração dos relatórios base.

    Solução: Modelagem de desduplicação por chave única no Power Query para garantir que contagens de projetos e bolsistas refletissem a realidade exata.

3. UX/UI e Design de Relatórios

    Padronização de KPI Cards no topo de cada aba para leitura imediata de totais.

    Utilização de Gráficos de Barras Horizontais ordenados para ranking visual limpo.

    Segmentadores de dados padronizados no formato Dropdown/Menu Suspenso para otimização de espaço.

Módulos do Dashboard

    Bolsistas IC: Acompanhamento de bolsas de Iniciação Científica, distribuição por modalidade e docentes.

    Estagiários: Visão geral da distribuição de estagiários pelos setores e institutos.

    Projetos de Extensão: Análise financeira, temporal e alcance das atividades extensionistas.

    Grupos de Pesquisa: Mapeamento de grupos cadastrados, líderes de pesquisa e distribuição por institutos.

    Projetos de Pesquisa: Análise histórica por ano, órgãos financiadores (CNPq, FAPEMIG, CAPES) e unidades coordenadoras.

Tecnologias Utilizadas

    Power BI Desktop: Construção do layout, dashboards e navegação.

    Power Query (Linguagem M): Limpeza, unificação, tratamento de encoding e transformações.

    DAX: Criação de medidas agregadas, contagens distintas e médias dinâmicas.

Como Visualizar o Projeto

    Faça o clone deste repositório:
    Bash

    git clone https://github.com/seu-usuario/nome-do-repositorio.git

    Abra o arquivo .pbix na pasta principal utilizando o Power BI Desktop.

    (Opcional) As bases limpas utilizadas estão disponíveis na pasta data/.
