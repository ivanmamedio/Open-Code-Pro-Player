---
name: Segurança
description: Boas práticas de segurança de software e código seguro
metadata:
  opencode/autoinvoke: false
---

# Skill: Segurança

Esta skill contém diretrizes de segurança para desenvolvimento de software. Sempre que avaliar ou escrever código, aplique as práticas abaixo e avise o usuário sobre riscos identificados.

## 1. Gerenciamento de Segredos
- **Nunca exponha segredos no código**: senhas, chaves de API, tokens, private keys e strings de conexão não devem estar hardcoded.
- Use variáveis de ambiente (`process.env`, `.env`), secrets do CI/CD ou gerenciadores de secrets (AWS Secrets Manager, Azure Key Vault, HashiCorp Vault).
- Nunca commite arquivos `.env` com valores reais no Git. Use `.env.example` como modelo.

## 2. Validação e Sanitização de Entrada
- Valide **tudo** que vem do usuário: parâmetros de URL, corpo da requisição, headers, cookies, arquivos enviados.
- Use listas de permissões (allowlist) em vez de listas de bloqueio (blocklist).
- Sanitize dados antes de exibi-los na interface para evitar XSS.
- Use consultas parametrizadas/prepared statements para evitar injeção SQL.
- Valide tipos, tamanhos, formatos e ranges de dados.

## 3. Princípio do Mínimo Privilégio
- Conceda apenas as permissões estritamente necessárias para cada usuário, serviço ou processo.
- Contas de serviço devem ter acesso restrito ao necessário.
- Revise permissões regularmente e remova acessos desnecessários.

## 4. Autenticação e Autorização
- Implemente autenticação forte (MFA quando possível).
- Use sessões seguras (cookies HttpOnly, Secure, SameSite).
- Valide tokens JWT (assinatura, expiração, emissor).
- Implemente controle de acesso baseado em papel (RBAC) ou atributos (ABAC).
- Nunca confie no cliente para decisões de autorização; valide sempre no servidor.

## 5. Criptografia
- Use HTTPS/TLS para toda comunicação em trânsito.
- Hash de senhas com algoritmos fortes: bcrypt, Argon2 ou scrypt. Nunca MD5, SHA1 ou texto puro.
- Use sal (salt) único por senha.
- Criptografe dados sensíveis em repouso quando necessário.
- Não invente seu próprio algoritmo de criptografia; use bibliotecas padrão e auditadas.

## 6. Gerenciamento de Dependências
- Mantenha dependências atualizadas.
- Execute auditorias de vulnerabilidade regularmente (`npm audit`, `yarn audit`, `pip audit`, etc.).
- Remova dependências não utilizadas.
- Verifique a integridade de pacotes (checksums, assinaturas quando disponível).

## 7. Tratamento de Erros e Logging
- Não exponha detalhes internos (stack traces, caminhos de arquivos, queries SQL) ao usuário final.
- Logs devem registrar erros internos sem incluir dados sensíveis (senhas, tokens, cartões de crédito).
- Use níveis de log apropriados (info, warn, error, debug).

## Checklist de Segurança
- [ ] Nenhum segredo hardcoded?
- [ ] Todas as entradas do usuário validadas e sanitizadas?
- [ ] Consultas ao banco usam prepared statements?
- [ ] Senhas hasheadas com algoritmo forte?
- [ ] HTTPS obrigatório?
- [ ] Permissões seguem mínimo privilégio?
- [ ] Erros não expõem detalhes internos?

Se qualquer item estiver em risco, avise o usuário antes de prosseguir com a implementação.