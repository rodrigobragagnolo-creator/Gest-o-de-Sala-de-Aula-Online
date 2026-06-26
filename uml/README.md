# UML

Esta pasta contém diagramas UML do sistema.

## Objetivo

Representar graficamente a interação entre atores e funcionalidades principais do software, fomentar as regras de negócio e a aplicabilidade do produto, conforme camadas de segurança pré-definidas pelo administrador/TI 

## Diagramas

- `casos-de-uso.png` → principais casos de uso do sistema

## Atores principais
temos por requesito logon no sistema com status "usuário abstrato" onde após logar o usuário recebe o status "usuário autenticado" que pode ser:

- Aluno
- Professor
- Coordenador
- Administrador/TI

## Casos de uso principais Aluno ##

- recebe a restrição de vínculo por perfil mais inferior;
- VISUALIZA: atividades, avisos, histórico de notas exclusivo de turmas que esteja matriculado;
- SUBMETE: arquivos para atividades de turmas que está matriculado, respeitando a regra de negócio RN02;
- NÃO VISUALIZA: nota de colegas, notas próprias não liberadas pelo professor, respeitando a RN05, onde a automação é disparada após o lote de turmas ser alimentado com todas as notas de uma vez só;
- NÃO ALTERA: a própria nota, conteúdo de atividade postados pelo professor;
- ALTERA: o próprio conteúdo que realizou upload para o sistema, sem limite de comentários.
  
## Casos de uso principais Professor ##
- possui privilégio de escrita (criação e modificação restritoaos conjuntos de turma que foi designado pelo coordenador e vinculado pelo administrativo/TI.
- VISUALIZA: materiais, atividades, murais das turmas sob sua responsabilidade
- recebe a submissão de alunos matriculados em suas turmas;
- lança notas: tem uma janela de 7 dias após a publicação inicial da nota atendendo a RN03 para que o aluno possa solicitar por seu acesso uma retificação, mas exige justificativa formal e aprovação pelo coordenador, a retificação da nota atende pela extensão (UC08a).
- controla a visibilidade de notas: pelo comando UC09 de liberação em lote e em conformidade com a RN05.
- NÃO PODE: alterar conteúdo de outros professores, aprovar suas próprias solicitações de retificação, acessar logs de auditoria de segurança do sistema ou configurações de REBAC. Além disso, não pode excluir permanentemente conteúdo, toda a exclusão resulta em soft delete, com o extensão do comando (UC07a) e não podendo excluir arquivos dos alunos.



