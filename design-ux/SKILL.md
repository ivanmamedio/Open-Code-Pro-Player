---
name: Design e UI/UX
description: Diretrizes de interface do usuário, experiência do usuário e acessibilidade
metadata:
  opencode/autoinvoke: false
---

# Skill: Design e UI/UX

Esta skill contém diretrizes de design, interface e experiência do usuário. Ao sugerir interfaces, componentes ou fluxos de aplicação, aplique os princípios abaixo.

## 1. Hierarquia Visual
- Use tamanho, cor, contraste e espaço para estabelecer a ordem de importância dos elementos.
- O elemento mais importante da página deve ser o mais proeminente.
- Agrupe elementos relacionados por proximidade.

## 2. Consistência
- Mantenha cores, tipografia, espaçamento, bordas e componentes padronizados em toda a aplicação.
- Use um sistema de design ou biblioteca de componentes consistente (ex: Material Design, Ant Design, shadcn/ui, Tailwind).
- Botões, inputs e modais devem ter o mesmo comportamento em todas as telas.

## 3. Acessibilidade (a11y)
- Contraste mínimo WCAG AA (4.5:1 para texto normal, 3:1 para texto grande).
- Todos os campos devem ter labels visíveis e associados (`<label>` ou `aria-label`).
- Navegação completa por teclado (Tab, Enter, Espaço, Esc).
- Imagens devem ter `alt` descritivo ou `aria-hidden="true"` se decorativas.
- Use elementos semânticos HTML (`<button>`, `<nav>`, `<main>`, `<section>`, `<footer>`).
- Foque visível em elementos interativos.

## 4. Mobile-First e Responsividade
- Projete primeiro para telas pequenas, depois expanda para desktop.
- Use breakpoints consistentes (ex: sm, md, lg, xl).
- Botões e áreas de toque devem ter pelo menos 44x44px.
- Evite hover-only interações em dispositivos móveis.

## 5. Feedback ao Usuário
- Estados de carregamento (spinners, skeletons) em ações assíncronas.
- Mensagens de erro claras, em linguagem do usuário, com sugestão de correção.
- Confirmações de ação bem-sucedidas (toasts, alertas, badges).
- Estado vazio (empty state) quando não há dados para exibir.

## 6. Usabilidade
- Minimize o número de cliques para completar uma tarefa.
- Use linguagem clara, direta e sem jargão técnico na interface.
- Forneça atalhos de teclado para ações frequentes.
- Permita desfazer ações destrutivas quando possível.
- Placeholder deve ser exemplo, não substituto de label.

## 7. Performance Percebida
- Carregue conteúdo crítico primeiro.
- Use lazy loading para imagens e componentes não críticos.
- Forneça feedback imediato em interações (estados de pressionado, hover).

## Checklist de UI/UX
- [ ] A interface é responsiva e funciona em mobile?
- [ ] O contraste atende aos padrões de acessibilidade?
- [ ] Todos os elementos interativos são navegáveis por teclado?
- [ ] Há feedback de carregamento, erro e sucesso?
- [ ] A linguagem é clara e amigável ao usuário?
- [ ] O design é consistente com o restante da aplicação?

Sempre que sugerir código de interface, inclua considerações de acessibilidade e responsividade.