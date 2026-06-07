# Changelog - PromptFlow

## CORREÇÃO CRÍTICA - Separação de Contextos

### 🔴 Problema Identificado
A aplicação estava **misturando** as regras do PromptFlow (a ferramenta) com as regras do prompt que o PromptFlow gera para outras aplicações.

### ✅ Solução Implementada
Separação clara entre:

**PromptFlow (a ferramenta em si):**
- ❌ Não tem backend
- ❌ Não tem Supabase
- ❌ Não tem banco de dados
- ❌ Não tem login
- ❌ Não salva dados
- ✅ É apenas uma ferramenta client-side para gerar prompts

**Aplicações geradas pelo PromptFlow:**
- ✅ Podem usar React + Vite
- ✅ Podem usar shadcn/ui
- ✅ Podem usar Supabase
- ✅ Podem ter SQL completo
- ✅ Podem ter autenticação (se selecionado)

---

# Changelog - PromptFlow

## Ajustes Realizados

### ✅ 1. Corrigido Bloco [BANCO DE DADOS]
- **Texto atualizado:** "Toda persistência **da aplicação gerada** deve utilizar Supabase"
- Deixa claro que é sobre a aplicação que será construída, não sobre o PromptFlow
- **Regras:**
  - Não utilizar banco local
  - Não utilizar SQLite
  - Não utilizar JSON como persistência final
  - Gerar SQL completo para Supabase (tabelas, relacionamentos, constraints, índices, RLS)

### ✅ 2. Corrigido Pacote SaaS
**Carrega SOMENTE:**
- ✅ Autenticação de Usuários (login, cadastro, recuperação)
- ✅ Dashboard do Usuário
- ✅ Configurações do Usuário
- ✅ Proteção de Rotas

**NÃO carrega automaticamente:**
- ❌ Pagamentos
- ❌ Assinaturas
- ❌ Painel Admin
- ❌ Papéis e Permissões
- ❌ Logs
- ❌ Exportação
- ❌ Alternância de Tema

### ✅ 3. Corrigido Pacote Landing Page
**Carrega SOMENTE:**
- ✅ Seção Hero
- ✅ Seção de Funcionalidades
- ✅ Perguntas Frequentes (FAQ)
- ✅ Formulário de Contato
- ✅ Rodapé

**NÃO carrega automaticamente:**
- ❌ Tabela de Preços

### ✅ 4. Corrigido Formulário de Contato
- **Antes:** "integração com serviço de envio de email ou banco de dados"
- **Agora:** "Caso nenhuma integração externa seja definida, não implementar serviço de envio real nem backend próprio"

### ✅ 4. Adicionados Pacotes Dashboard e CRUD

**Pacote Dashboard carrega SOMENTE:**
- ✅ Métricas e Gráficos
- ✅ Filtros
- ✅ Relatórios

**NÃO carrega automaticamente:**
- ❌ Exportação de Dados
- ❌ Painel Admin
- ❌ Notificações

**Pacote CRUD carrega SOMENTE:**
- ✅ Tabelas de Dados
- ✅ Formulários de CRUD
- ✅ Busca
- ✅ Paginação

**NÃO carrega automaticamente:**
- ❌ Exportação
- ❌ Notificações
- ❌ Painel Admin

### ✅ 5. Funcionalidades Extras Disponíveis
As funcionalidades extras aparecem **APENAS se não vieram dos pacotes selecionados**:

- Pagamentos
- Assinaturas
- Tabela de Preços
- Painel Admin
- Papéis e Permissões
- Logs de Atividades
- Upload de Arquivos
- Notificações
- Integração WhatsApp
- Exportar PDF
- Exportar CSV/Excel
- Alternância de Tema
- Tabelas Avançadas
- Formulários Dinâmicos

**Comportamento:** Funcionalidades extras só aparecem no prompt final se forem explicitamente selecionadas pelo usuário.

### ✅ 6. Melhorado Design & UX no Prompt
O bloco `[DESIGN E EXPERIÊNCIA]` agora inclui:
- Liberdade de Adaptação Mobile
- Referência Visual (campo adicional no formulário)
- Prioridades Visuais

### ✅ 6. Melhorado Design & UX no Prompt
O bloco `[DESIGN E EXPERIÊNCIA]` inclui:
- Preset Shadcn/UI
- Fidelidade ao Preset
- Tema Inicial
- Estilo Visual
- Estratégia Responsiva
- **Liberdade de Adaptação Mobile** (corrigido)
- Referência Visual (se preenchida)
- Prioridades Visuais (se preenchidas)

### ✅ 7. Corrigido Stack e Arquitetura
**Texto atualizado para deixar claro que é sobre a aplicação GERADA:**
- Frontend: React, Vite, TypeScript, Tailwind CSS, shadcn/ui
- Backend/BaaS: Supabase para banco de dados, autenticação e storage quando necessário
- Não criar backend próprio local
- Não criar banco de dados local

### ✅ 8. Combinações Geram Apenas Contexto Arquitetural
- ✅ Combinações adicionam orientações sobre estrutura
- ❌ Combinações NÃO adicionam funcionalidades extras
- **Exemplo:** "SaaS + Landing Page" = contexto sobre integração de área pública e privada
- Usuário tem controle total sobre quais funcionalidades incluir

### ✅ 9. Interface Mantida
- Visual limpo e profissional preservado
- Cor principal #3B82F6 mantida
- Branding "◈ PromptFlow" intacto
- Responsividade garantida
- Modal fullscreen e botão copiar funcionando

---

## 🔑 Princípio Fundamental Corrigido

**ANTES:** PromptFlow misturava suas próprias limitações com as especificações da aplicação gerada.

**AGORA:** 
- ✅ PromptFlow é uma ferramenta client-side simples
- ✅ O prompt gerado especifica aplicações full-stack robustas com Supabase
- ✅ Separação clara de contextos

---

## Arquivos Modificados

1. `src/data/packages.json` - Corrigidas features de TODOS os pacotes (SaaS, Landing Page, Dashboard, CRUD)
2. `src/data/features.json` - Adicionadas novas features e separação clara (base vs. extras)
3. `src/data/global-rules.json` - Regras agora são claras sobre aplicação GERADA
4. `src/engine/prompt-engine.ts` - Blocos STACK e BANCO DE DADOS reescritos
5. `src/pages/GeneratorPage.tsx` - Interface de funcionalidades extras funcional
6. `README.md` - Documentação atualizada com separação de contextos

---

## ✅ Resultado Final

**Exemplo prático:**
- Selecionar: SaaS + Landing Page + CRUD + Dashboard
- **Não inclui automaticamente:** Pagamentos, Admin, Exportação, Notificações, Tema
- **Inclui apenas:** Auth, Dashboard Usuário, Config, Hero, FAQ, Contato, Rodapé, Tabelas, Forms, Busca, Paginação, Métricas, Filtros, Relatórios
- Usuário pode adicionar extras explicitamente

Build: ✅ Passou  
Lógica: ✅ Corrigida  
Visual: ✅ Mantido