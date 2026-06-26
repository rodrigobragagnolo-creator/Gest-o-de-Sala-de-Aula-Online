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
- visualiza: atividades, avisos, histórico de notas exclusivo de turmas que esteja matriculado;
- submete: arquivos para atividades de turmas que está matriculado, respeitando a regra de negócio RN02;
- não visualiza: nota de colegas, notas próprias não liberadas pelo professor, respeitando a RN05, onde a automação é disparada após o lote de turmas ser alimentado com todas as notas de uma vez só;
- não altera: a própria nota, conteúdo de atividade postados pelo professor;
- altera: o próprio conteúdo que realizou upload para o sistema, sem limite de comentários.



