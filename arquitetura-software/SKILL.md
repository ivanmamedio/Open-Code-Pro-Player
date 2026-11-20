---
name: Arquitetura de Software
description: Diretrizes de arquitetura de software, padrões de projeto e engenharia de software
metadata:
  opencode/autoinvoke: false
---

# Skill: Arquitetura de Software

Esta skill contém diretrizes para avaliar, projetar e revisar código com foco em arquitetura de software e engenharia de software. Sempre que o usuário solicitar criação, revisão ou alteração de código, aplique os princípios abaixo.

## Princípios Fundamentais

### 1. Princípios SOLID
- **S** - Single Responsibility Principle (SRP): Cada classe/módulo deve ter uma única responsabilidade.
- **O** - Open/Closed Principle (OCP): Entidades devem estar abertas para extensão, fechadas para modificação.
- **L** - Liskov Substitution Principle (LSP): Objetos de uma classe derivada devem poder substituir objetos da classe base sem quebrar o programa.
- **I** - Interface Segregation Principle (ISP): Interfaces específicas são melhores que interfaces gerais.
- **D** - Dependency Inversion Principle (DIP): Dependa de abstrações, não de implementações concretas.

### 2. Separação de Camadas
Mantenha as camadas desacopladas:
- **Apresentação (UI/Controller)**: Interface com o usuário, recebe entradas e exibe saídas.
- **Negócio (Service/Use Case)**: Regras de negócio, validações e orquestração.
- **Dados (Repository/DAO)**: Acesso a banco de dados, arquivos e APIs externas.
- **Infraestrutura**: Configuração, logging, envio de e-mails, autenticação, etc.

### 3. Baixo Acoplamento, Alta Coesão
- Módulos devem ser independentes entre si (baixo acoplamento).
- Elementos dentro de um módulo devem estar fortemente relacionados (alta coesão).
- Evite dependências circulares.

### 4. Padrões de Projeto Comuns
Use quando apropriado:
- **Factory**: Criação de objetos sem expor a lógica de instantição.
- **Strategy**: Algoritmos intercambiáveis em tempo de execução.
- **Repository**: Abstração de acesso a dados.
- **Observer**: Notificação de mudanças entre objetos.
- **Adapter**: Integração de interfaces incompatíveis.
- **Decorator**: Adição de comportamento dinâmico a objetos.

### 5. Testabilidade
- Código deve ser fácil de testar unitariamente.
- Use injeção de dependência para facilitar mocks.
- Separe lógica de negócio de efeitos colaterais (I/O, rede, banco).

### 6. Documentação de Decisões
- Registre decisões de arquitetura importantes (ADRs - Architecture Decision Records).
- Documente interfaces públicas e contratos de API.

## Checklist Antes de Sugerir Código
- [ ] A solução respeita os princípios SOLID?
- [ ] As camadas estão bem separadas?
- [ ] O acoplamento é baixo e a coesão é alta?
- [ ] O código é testável?
- [ ] Há documentação suficiente para outro desenvolvedor entender?

Se a resposta for não para qualquer item, sugira refatoração antes de prosseguir.