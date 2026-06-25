Decisões Arquiteturais

DA01 — Arquitetura em Camadas

Decisão: utilizar arquitetura em camadas, separando apresentação, regras de negócio, acesso a dados e banco de dados.

Justificativa: o sistema ClassFlow possui funcionalidades típicas de aplicação web, como login, turmas, atividades, entregas, correções e notificações. A arquitetura em camadas facilita a organização do código, a manutenção e a separação de responsabilidades.

Impacto: melhora a clareza da solução e permite evoluir o sistema sem misturar interface, regras de negócio e persistência de dados.



DA02 — Autenticação com controle de perfis

Decisão: o sistema terá autenticação de usuários e controle de acesso por perfil: estudante, professor, coordenador e administrador.

Justificativa: diferentes usuários possuem permissões diferentes. Por exemplo, apenas professores podem criar atividades, estudantes podem entregar atividades e administradores podem gerenciar usuários.

Impacto: atende requisitos de segurança e garante que cada usuário acesse apenas as funcionalidades permitidas ao seu papel.



DA03 — Notificações assíncronas

Decisão: o sistema utilizará um serviço de notificações separado para avisos sobre novas atividades, prazos, correções e comunicados.

Justificativa: notificações não precisam bloquear o uso principal do sistema. Ao separar essa responsabilidade, a plataforma continua funcionando mesmo se o envio de notificações atrasar ou falhar temporariamente.

Impacto: melhora a experiência do usuário, reduz acoplamento entre módulos e permite evoluir futuramente para e-mail, push ou notificações internas.
