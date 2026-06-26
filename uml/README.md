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
- possui privilégio de escrita (criação e modificação restritoaos conjuntos de turma que foi designado pelo coordenador e vinculado pelo administrativo/TI;
- VISUALIZA: materiais, atividades, murais das turmas sob sua responsabilidade;
- recebe a submissão de alunos matriculados em suas turmas;
- lança notas: tem uma janela de 7 dias após a publicação inicial da nota atendendo a RN03 para que o aluno possa solicitar por seu acesso uma retificação, mas exige justificativa formal e aprovação pelo coordenador, a retificação da nota atende pela extensão (UC08a);
- controla a visibilidade de notas: pelo comando UC09 de liberação em lote e em conformidade com a RN05;
- NÃO PODE: alterar conteúdo de outros professores, aprovar suas próprias solicitações de retificação, acessar logs de auditoria de segurança do sistema ou configurações de REBAC. Além disso, não pode excluir permanentemente conteúdo, toda a exclusão resulta em soft delete, com o extensão do comando (UC07a) e não pode excluir arquivos dos alunos.

## Casos de uso principais Coordenador ##
- usuário com papel de supervisão pedagógica, abrange múltiplos professores com permissão administrativa.
- abraange múltiplas turmas e múltiplos professores;
- emite relatórios de desempenho (UC10);
- aprova pedido de retificação de nota (UC11);
- audita qualquer conteúdo excluído, com acesso a permanência do banco de dados (UC12);
- NÃO PODE: coordenador não tem permissões de escrita direta, ou são nulas;
- exerce supervisão e aprovação;
- NÃO EXECUTA: criar atividades, lançar notas;
- VISUALIZA: Dados de desempenho, médias, taxas de entrega, taxas de evasão, itens com soft delete respeitando a RN06 das turmas supervisionadas;
- PODE APROVAR/REJEITAR: Solicitações de retificação, exigêncial formal pela RN03 para alteração de nota após a janela de 7 dias corridos;
- NÃO PODE: lançar notas em nome de um professor, criar ou excluir atividades em turmas que não são suas, mas pode auditar e gerar relatórios. Não pode acessar configurações de papéis e permissões RBAC (UC13) OU logs de segurança de infra-estrutura,pois são competências do ator administrador.

Distinção crítica entre coordenador vs. administrador/TI:
coordenador-> governança pedagógica
- qualidade do ensino
- conformidade com políticas academicas.

administrador-> governança técnica
- infraestrutura
- segurança
- provisionamento

Dessa forma, evitamos concentração excessiva de poder em um único papel.
  
## Casos de uso principais Administrador/TI ##
Usuário de TI/suporte responsável pela configuração estrutural do sistema, faz a gestão de identidades camadas e papéis, provisionamento de turmas em lotes e auditoria de segurança técnica.
- gerencia papéis e permissões (UC13)
- provisiona turmas em lotes (UC14)
- Auditar logs de acesso e segurança (UC15).

  Fronteira de segurança (RBAC)
  O ADM possui o nível mais elevado do sistema, mas não pode ler o conteúdo das atividades, submissões de estudantes ou notas individuais, separando muito bem a gestão de administração de infraestrutura e gestão pedagógica.
PODE GERENCIAR:
Matriz de papéis, permissões do sistema, atribuição/revogação de papéis a usuários;
ciclo de vida estrutural de turmas em lote;
vinculação automática de professores e estudantes apartir de integração com sistema de registro acadêmico.
PODE AUDITAR:
logs de acesso ou tentativas bem sucedidas ou negadas, incluso tentativas de violação da RN01 (acesso a turma sem vínculo).
NÃO PODE: por desenho, não apenas por ausência de casos de uso modelado
- lançar ou alterar notas;
- criar ou publicar atividade pedagógica;
- aprovar retificações extemporâneas que são exclusivas ao coordenador.No caso a RN03 é uma política institucional, não apenas restrição de interface, violar com acesso técnico liberado constitui desvio de processo.

  Nota de design de segurança:
  A separação entre adm e coordenador reflete o princípio de segregação de funções (separation of duties) mitigando o risco de um único papel ou ator ser capaz de alterar infraestrutura de permissões quanto aprovar excessões de avaliação acadêmica.

  


