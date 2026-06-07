# PromptFlow

Uma ferramenta poderosa para geração de prompts estruturados para IAs que criam aplicações web.

## 🚀 Sobre

O PromptFlow é uma ferramenta client-side (sem backend) focada em desenvolvedores e criadores que utilizam IA (Lovable, Bolt, Replit, ChatGPT, etc) para gerar aplicações. Ele garante que você não esqueça regras importantes, requisitos de design ou funcionalidades antes de iniciar a geração de código.

**Importante:** PromptFlow não salva dados, não tem autenticação e não usa banco de dados. É apenas um gerador de prompts. As aplicações que você cria com os prompts gerados pelo PromptFlow é que terão backend, Supabase, autenticação, etc.

## 🛠️ Tecnologias Utilizadas

- **React** (v19)
- **Vite**
- **TypeScript**
- **Tailwind CSS** (v4)
- **shadcn/ui** (Componentes Radix + Tailwind)
- **Lucide Icons**

## 📂 Estrutura do Projeto

A aplicação é puramente *client-side*, sem backend ou banco de dados. Toda a configuração é mantida em arquivos JSON fáceis de editar.

- \`src/data/...\` - O coração da ferramenta. Edite esses JSONs para adicionar novos pacotes, funcionalidades e regras globais.
- \`src/engine/prompt-engine.ts\` - O motor que lê os dados selecionados, formata e compõe o prompt final.
- \`src/pages/...\` - Páginas principais (Landing e Generator).
- \`src/components/ui/...\` - Componentes reutilizáveis no padrão shadcn/ui.

## 📦 Como Instalar e Executar

1. Clone o repositório ou baixe os arquivos.
2. Certifique-se de ter o Node.js instalado (v18+).
3. Instale as dependências:
   \`\`\`bash
   npm install
   \`\`\`
4. Inicie o servidor de desenvolvimento:
   \`\`\`bash
   npm run dev
   \`\`\`
5. Acesse no seu navegador através de \`http://localhost:5173\`.

## 📈 Como Evoluir o Projeto

- **Adicionar Novos Pacotes:** Edite o arquivo \`src/data/packages.json\`.
- **Adicionar Novas Funcionalidades:** Edite o arquivo \`src/data/features.json\`.
- **Criar Novas Combinações Inteligentes:** Edite \`src/data/combinations.json\`.
- **Adicionar Regras Globais Fixas:** Edite \`src/data/global-rules.json\`.
- **Melhorar Motor de Prompts:** Edite \`src/engine/prompt-engine.ts\`.

A arquitetura foi pensada para ser escalável. Se no futuro for necessário adicionar salvamento em nuvem ou histórico de prompts, basta conectar uma API ou Supabase ao estado gerenciado no \`GeneratorPage.tsx\`.

## 🎯 Qualidade dos Prompts

O PromptFlow v1 inclui refinamentos para garantir prompts de alta qualidade:

- **Processo de Análise:** A IA analisa requisitos antes de codificar
- **Validação Final:** Checklist para garantir completude
- **SQL Robusto:** Instruções para criar schemas completos e escaláveis
- **Entrega Completa:** Zero pseudocódigo, zero TODOs
- **Simplicidade:** Prioriza soluções simples sobre complexas

## 🎨 Controle Visual Avançado

Personalize completamente a identidade visual das aplicações geradas:

- **Cor Principal:** Defina cores por nome, HEX, RGB (ex: "Azul esmeralda", "#3B82F6")
- **Estilo da Solução:** Escolha a personalidade (Premium, Tecnológica, Minimalista, etc.)
- **Referência Visual:** Use sites reais como inspiração (Spotify, Linear, Stripe)
- **Estilo Visual:** Minimalista, Corporativo, Moderno, etc.
- **Controle Responsivo:** Mobile-first, Desktop-first, etc.

## 🛡️ Validação Inteligente

O PromptFlow garante que você não gere prompts incompletos:

- **Campos Obrigatórios:** Nome e Descrição do projeto são sempre necessários
- **Estrutura Mínima:** Exige pelo menos 1 pacote, 1 funcionalidade extra OU 1 funcionalidade personalizada
- **Feedback Instantâneo:** Toast messages claras indicam o que precisa ser preenchido
- **Botão Inteligente:** Desabilita automaticamente quando requisitos não são atendidos
- **Dupla Proteção:** Validação visual + validação programática"# prompt-flow" 
