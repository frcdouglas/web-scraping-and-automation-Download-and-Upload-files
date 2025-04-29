# Automação de Download de Modelos STL para Clínica Odontológica

## 📋 Descrição do Projeto

Automação desenvolvida com Python, Selenium e PyAutoGUI para realizar o download automático de modelos STL em uma clínica de radiologia odontológica. O sistema realiza login, baixa modelos e organiza arquivos sem intervenção humana, sendo executado automaticamente ao final do expediente.

## 🔍 Problema Resolvido

### Desafios Anteriores:
- **Tempo Consumido**: Aproximadamente 30 minutos diários gastos em tarefas manuais repetitivas
- **Erros de Nomeação**: Frequentes trocas de nomes nas pastas de pacientes
- **Atrasos na Disponibilização**: Arquivos disponíveis apenas no dia seguinte
- **Interrupções no Trabalho**: Funcionários recebiam ligações frequentes solicitando arquivos

### Processo Manual Original:
Um funcionário realizava todo o procedimento manualmente, incluindo login no site do scanner, download dos modelos um por um e renomeação das pastas. O processo era lento, especialmente porque o sistema da nuvem abria um software específico para exportar os arquivos.

## 💻 Solução Implementada

### Tecnologias Utilizadas:
- **Python**: Linguagem base para o desenvolvimento
- **Selenium**: Automação da navegação e interações web
- **PyAutoGUI**: Automação de interações com interfaces desktop
- **Windows Task Scheduler**: Agendamento de execução automática

### Funcionalidades:
- Login automático no sistema do scanner
- Download sequencial dos modelos STL
- Renomeação automática das pastas com informações corretas dos pacientes
- Execução programada diária às 20h após o expediente
- Operação sem necessidade de intervenção humana

## 🛠️ Desafios Técnicos e Soluções

### Principais Desafios:
- **Código Monolítico**: Na primeira versão, todas as operações estavam em um único arquivo
- **Múltiplos Ambientes**: Necessidade de interagir com interfaces web e desktop
- **Complexidade do Processo**: Mapeamento preciso da sequência de ações necessárias

### Soluções Implementadas:
- **Padrão Page Object Model (POM)**: Refatoração do código para uma estrutura mais organizada e manutenível
- **Integração Selenium + PyAutoGUI**: Combinação eficiente para lidar com os diferentes ambientes
- **Mapeamento Detalhado**: Análise cuidadosa de cada etapa do processo para automação eficiente
- **Tratamento de Exceções**: Implementação de mecanismos robustos para garantir a confiabilidade

## 📊 Resultados e Impacto

### Benefícios Quantitativos:
- **Economia de Tempo**: 30 minutos diários (aproximadamente 10 horas mensais)
- **Eliminação de Erros**: 100% dos erros de nomeação de arquivos eliminados
- **Disponibilização Rápida**: Modelos disponíveis no mesmo dia do escaneamento

### Benefícios Qualitativos:
- **Otimização de Recursos Humanos**: Funcionário redirecionado para tarefas de maior valor
- **Redução de Interrupções**: Diminuição significativa de ligações solicitando arquivos
- **Satisfação do Cliente**: Melhoria na experiência dos dentistas parceiros
- **Ambiente de Trabalho**: Redução de estresse na equipe de atendimento

## 🏗️ Estrutura do Projeto

```
/automacao_stl/
│
├── main.py                # Arquivo principal que inicia a automação
├── images/                # Imagens utilizadas para localizar elementos com PyAutoGui
├── pages/
│   ├── __init__.py
│   ├── login_page.py      # Página de login do sistema
│   ├── lista_pacientes.py # Página com lista de pacientes
│   └── exporter_page.py   # Página do exportador de STL
├── utils/
│   ├── __init__.py
│   ├── logger.py          # Utilitário para logs
│   └── file_handler.py    # Utilitário para manipulação de arquivos
└── README.md              # Documentação do projeto
```

## 🧠 Abordagem de Desenvolvimento

O projeto foi implementado utilizando o padrão Page Object Model (POM), que cria uma representação orientada a objetos das páginas web. Cada página do sistema é representada por uma classe separada que contém:

1. Localizadores dos elementos da interface
2. Métodos para interagir com esses elementos
3. Métodos que representam fluxos completos de operação

Esta abordagem trouxe os seguintes benefícios:
- **Manutenibilidade**: Facilidade para atualizar o código quando a interface muda
- **Legibilidade**: Estrutura clara que representa o fluxo do aplicativo
- **Reutilização**: Métodos modulares que podem ser combinados em diferentes fluxos

## 📈 Lições Aprendidas

- **Importância do Mapeamento**: Antes de iniciar a automação, é crucial mapear detalhadamente todos os processos
- **Valor da Refatoração**: A organização do código com padrões adequados facilita manutenção e expansão
- **Integração de Ferramentas**: A combinação de diferentes bibliotecas permite superar limitações individuais
- **Impacto no Negócio**: Mesmo automações aparentemente simples podem trazer ganhos significativos de eficiência
