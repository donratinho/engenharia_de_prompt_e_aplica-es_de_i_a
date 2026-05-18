1. Documentação Automática de Código Legado

O Problema Real: Desenvolvedores perdem semanas tentando entender sistemas antigos (código legado) sem documentação antes de implementar novas features ou corrigir bugs.

O Gap: Ferramentas atuais geram comentários simples de código, mas não explicam a arquitetura ou o impacto de alterar uma função em outras partes do sistema.

A Solução com IA (MVP): Uma extensão para o VS Code (ou uma plataforma web simples) onde o dev faz o upload de um arquivo ou repositório antigo. A IA analisa o código e gera um "Guia de Sobrevivência" em Markdown, explicando o que o código faz, as regras de negócio embutidas ali e os pontos críticos de atenção.

Por que é viável como MVP? Você pode usar a API do GPT-4o ou Claude 3.5 Sonnet com um prompt estruturado (System Prompt) especializado em engenharia reversa de código.
