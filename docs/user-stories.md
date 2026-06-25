# User Stories

## US01
Como professor, quero criar turmas para organizar meus alunos.

### Critérios de aceitação

- O professor deve estar autenticado.
- O sistema deve permitir informar nome e descrição da turma.
- O sistema deve gerar um código de acesso para alunos.
- Alunos não podem criar turmas.
- 
## US02
Como professor, quero publicar atividades.

### Critérios de aceitação

- O professor deve selecionar uma turma existente.
- A atividade deve conter título, descrição e prazo.
- O sistema deve notificar os alunos da turma.
- A atividade deve ficar visível aos alunos após a publicação.

## US03
Como aluno, quero entrar em uma turma usando código.

### Critérios de aceitação

- O aluno deve estar autenticado.
- O código informado deve existir e estar ativo.
- O aluno não deve ser incluído duas vezes na mesma turma.
  
## US04
Como aluno, quero enviar atividades.

### Critérios de aceitação

- A atividade deve estar dentro do prazo de entrega.
- O aluno deve pertencer à turma da atividade.
- O sistema deve registrar data e horário da entrega.
- Cada aluno deve ter apenas uma entrega ativa por atividade.

## US05
Como professor, quero corrigir atividades.

### Critérios de aceitação

- Apenas o professor da turma pode corrigir.
- A correção deve permitir nota e feedback.
- O sistema deve registrar a data da correção.
- O aluno deve conseguir visualizar o resultado depois da publicação.

## US06
Como aluno, quero visualizar minhas notas.

### Critérios de aceitação

- O aluno deve visualizar apenas suas próprias notas.
- A nota deve estar vinculada a uma atividade e turma.
- O feedback do professor deve ser exibido quando disponível.
- 
## US07
Como coordenador, quero gerar relatórios.

### Critérios de aceitação

- Apenas coordenadores autorizados podem acessar relatórios.
- O relatório deve permitir visualizar turmas, atividades e médias.
- O relatório não deve permitir alteração de notas.

## US08
Como aluno, quero receber notificações sobre atividades para não perder prazos importantes.

### Critérios de aceitação

- O sistema deve notificar quando uma atividade for publicada.
- O sistema deve notificar quando uma correção for disponibilizada.
- A notificação deve estar vinculada à turma e à atividade.

## US09
Como professor, quero receber sugestões de feedback geradas por IA para acelerar a correção das atividades.

### Critérios de aceitação

- A IA deve atuar apenas como apoio.
- A nota final deve ser confirmada pelo professor.
- O professor deve poder editar o feedback sugerido.
- A sugestão não deve ser enviada automaticamente ao aluno sem revisão humana.
