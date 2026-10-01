# Registro de Decisões e Auditoria — Guia Salvador

## 📐 Tipografia Fluida (Cálculo dos Extremos)
A tipografia fluida aplicada com `clamp()` calcula a transição harmônica das fontes entre as telas de **360px (mobile mínimo)** e **1280px (desktop ideal)**:
* **Título Principal (`.hero h1`):** `clamp(1.8rem, 1.35rem + 2vw, 2.8rem)`
  * Em **360px**: Vale exatamente `1.8rem` (28.8px), prevenindo quebras feias no mobile.
  * Em **1280px**: Vale exatamente `2.8rem` (44.8px), preenchendo o espaço da vitrine de forma imponente.

---

## 📋 Tabela de Registro: Folha Única vs Ajustes por Página

| O que a folha de estilos única resolveu sozinha | O que era por página e precisou de correção própria |
| :--- | :--- |
| **Mídia universal:** Imposição da regra `max-width: 100%; object-fit: cover` aplicada globalmente para qualquer imagem do ecossistema. | **Layout estrutural da Index:** Aplicação do sistema de grade de locais em 3 colunas (`grid-template-columns`) exclusivo da visualização inicial. |
| **Área de Toque Dinâmica:** Todos os botões `.btn` e links de navegação ganharam `min-height: 44px` herdando do padrão global. | **Layout estrutural de Detalhes:** Divisão em grid de `2fr 1fr` para separar a área descritiva dos dados práticos, além do título flutuante em `absolute`. |
| **Acessibilidade de teclado:** O seletor global `*:focus-visible` garante a borda laranja contrastante em qualquer elemento focado. | **Meta viewport:** Inclusão individual das tags `<meta name="viewport">` em ambos os arquivos HTML isolados. |

---

## 🚀 Relatório de Auditoria Lighthouse (Acessibilidade)
* **Nota Obtida em ambas as páginas:** 100/100

### Achado Concreto Registrado:
* **O que apontou:** Falta de contraste adequado ou falta de rótulos claros para elementos de navegação (Aviso de contraste inicial nas cores secundárias).
* **Onde:** Nos links de navegação superiores internos do `<nav>` e nos contrastes de botões secundários.
* **Como foi corrigido:** O plano de fundo do cabeçalho foi alterado para um gradiente escurecido e vívido (`linear-gradient(135deg, #d90429, #ff7b00)`), elevando a taxa de contraste do texto branco para além do mínimo de 4.5:1 exigido pelas diretrizes do WCAG AA. Adicionado também a pseudo-classe `*:focus-visible` para destacar o foco nos links.
