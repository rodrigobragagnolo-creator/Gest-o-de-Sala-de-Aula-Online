##  Arquitetura de Software Escolhida

A arquitetura principal escolhida para o ClassFlow é a **Arquitetura em Camadas**, organizada nos seguintes blocos:

1. **Camada de Apresentação** 
   Interface Web utilizada por alunos, professores, coordenadores e administradores.

2. **Camada de Aplicação / API** 
   Responsável por receber requisições da interface, aplicar regras de negócio e coordenar operações do sistema.

3. **Camada de Domínio** 
   Contém as regras centrais do ClassFlow, como criação de turmas, publicação de atividades, entrega, correção, notas e permissões.

4. **Camada de Persistência** 
   Responsável pelo acesso ao banco de dados e armazenamento das informações.

5. **Serviços auxiliares** 
   Serviço de notificações e módulo de correção assistida por IA.

---

## 5. Justificativa da arquitetura

A escolha por arquitetura em camadas é adequada porque o ClassFlow é um sistema acadêmico com regras bem definidas e fluxo de uso relativamente previsível.

Essa escolha favorece:

- organização clara do sistema;
- separação entre interface, regras de negócio e banco de dados;
- facilidade de entendimento para a equipe;
- menor complexidade inicial;
- boa manutenibilidade;
- possibilidade de evolução futura para serviços separados, caso o sistema cresça.



