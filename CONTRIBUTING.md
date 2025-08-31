# 🤝 Guia de Contribuição

Obrigado por considerar contribuir para a **n8n Automation Library**! Este guia irá ajudá-lo a entender como contribuir de forma eficaz.

---

## 🎯 Como Contribuir

### 📋 Tipos de Contribuição

- **🆕 Novos Workflows** - Crie automações para novas áreas
- **🔧 Melhorias** - Otimize workflows existentes
- **📚 Documentação** - Melhore guias e tutoriais
- **🐛 Correções** - Reporte e corrija bugs
- **💡 Sugestões** - Compartilhe ideias e feedback

---

## 🚀 Primeiros Passos

### 1️⃣ Fork o Repositório

1. **Acesse** [n8n-automation-library](https://github.com/matheusmelo-cabelo/n8n-automation-library)
2. **Clique em "Fork"** no canto superior direito
3. **Clone seu fork** localmente:
   ```bash
   git clone https://github.com/seu-usuario/n8n-automation-library.git
   cd n8n-automation-library
   ```

### 2️⃣ Configure o Ambiente

1. **Instale o n8n** (local ou cloud)
2. **Configure credenciais** de teste
3. **Teste workflows** existentes para entender a estrutura

### 3️⃣ Crie uma Branch

```bash
git checkout -b feature/nome-da-sua-feature
```

---

## 📝 Criando um Novo Workflow

### 🎯 Estrutura Recomendada

```
workflows/
└── categoria/
    ├── nome-do-workflow.json
    ├── README.md (opcional)
    └── config-example.json (opcional)
```

### 📋 Checklist de Qualidade

- [ ] **✅ Funciona** - Workflow testado e funcionando
- [ ] **📝 Documentado** - README com instruções claras
- [ ] **🔒 Seguro** - Sem credenciais hardcoded
- [ ] **🎯 Útil** - Resolve um problema real
- [ ] **🚀 Otimizado** - Performance adequada

### 📄 Template de Workflow

```json
{
  "name": "Nome do Workflow",
  "nodes": [
    {
      "parameters": {
        "name": "Trigger",
        "type": "trigger"
      },
      "id": "trigger-node",
      "name": "Trigger",
      "type": "n8n-nodes-base.trigger",
      "typeVersion": 1,
      "position": [240, 300]
    }
  ],
  "connections": {},
  "active": false,
  "settings": {},
  "versionId": "1"
}
```

---

## 📚 Documentação

### 📝 Padrões de Documentação

#### README de Categoria

```markdown
# 🎯 Nome da Categoria

Breve descrição da categoria e seus objetivos.

## 📋 Workflows Disponíveis

### 🔧 Nome do Workflow
**Arquivo**: `workflow-name.json`

**Funcionalidades**:
- ✅ Funcionalidade 1
- 📊 Funcionalidade 2
- 🔗 Funcionalidade 3

**APIs Necessárias**:
- API 1 (para funcionalidade)
- API 2 (para dados)

**Configuração**:
```json
{
  "config": "exemplo"
}
```
```

#### README de Workflow

```markdown
# 🔧 Nome do Workflow

Descrição detalhada do que o workflow faz.

## 🚀 Como Usar

1. Importe o arquivo `.json`
2. Configure as credenciais
3. Personalize conforme necessário
4. Ative o workflow

## ⚙️ Configuração

### Credenciais Necessárias

- **API Key**: Descrição
- **Webhook URL**: Descrição

### Variáveis de Ambiente

```bash
export WORKFLOW_API_KEY="sua-chave"
export WORKFLOW_WEBHOOK="sua-url"
```

## 🔧 Personalização

Exemplos de como personalizar o workflow.

## 🚨 Solução de Problemas

Problemas comuns e soluções.
```

---

## 🔧 Desenvolvimento

### 🛠️ Ferramentas Recomendadas

- **n8n** - Para criar e testar workflows
- **VS Code** - Editor de código
- **Postman** - Testar APIs
- **Git** - Controle de versão

### 📋 Checklist de Desenvolvimento

- [ ] **🧪 Teste** o workflow completamente
- [ ] **📝 Documente** todas as funcionalidades
- [ ] **🔒 Remova** credenciais sensíveis
- [ ] **🎯 Otimize** performance
- [ ] **📱 Teste** em diferentes cenários

### 🔍 Testes

#### ✅ Testes Obrigatórios

1. **Funcionalidade** - Workflow executa corretamente
2. **Erro Handling** - Trata erros adequadamente
3. **Performance** - Executa em tempo razoável
4. **Segurança** - Não expõe dados sensíveis

#### 🧪 Testes Recomendados

1. **Cenários Extremos** - Dados inválidos, APIs offline
2. **Volume** - Muitos dados simultâneos
3. **Integração** - Com outras ferramentas
4. **Usabilidade** - Fácil de configurar

---

## 📤 Enviando Contribuições

### 1️⃣ Prepare sua Contribuição

```bash
# Adicione suas mudanças
git add .

# Faça commit com mensagem descritiva
git commit -m "feat: adiciona workflow de automação de email

- Implementa automação de envio de emails
- Adiciona templates personalizáveis
- Inclui documentação completa
- Testa com dados reais"

# Envie para seu fork
git push origin feature/nome-da-sua-feature
```

### 2️⃣ Crie um Pull Request

1. **Acesse** seu fork no GitHub
2. **Clique em "Compare & pull request"**
3. **Preencha o template** de PR:

```markdown
## 📝 Descrição

Breve descrição das mudanças.

## 🎯 Tipo de Mudança

- [ ] 🆕 Nova funcionalidade
- [ ] 🔧 Melhoria
- [ ] 🐛 Correção de bug
- [ ] 📚 Documentação
- [ ] 🎨 Refatoração

## ✅ Checklist

- [ ] Código testado e funcionando
- [ ] Documentação atualizada
- [ ] Sem credenciais expostas
- [ ] Segue padrões do projeto

## 📸 Screenshots (se aplicável)

Adicione screenshots se relevante.

## 🔗 Links Relacionados

Issues relacionadas ou documentação.
```

### 3️⃣ Revisão e Merge

1. **Aguarde revisão** da equipe
2. **Responda feedback** se necessário
3. **Faça ajustes** se solicitado
4. **Aguarde merge** após aprovação

---

## 📋 Padrões do Projeto

### 🏗️ Estrutura de Arquivos

```
n8n-automation-library/
├── workflows/
│   ├── categoria-1/
│   │   ├── workflow-1.json
│   │   └── README.md
│   └── categoria-2/
│       ├── workflow-2.json
│       └── README.md
├── docs/
│   ├── how-to-import.md
│   ├── customization-tips.md
│   └── security-best-practices.md
├── README.md
├── CONTRIBUTING.md
└── LICENSE
```

### 📝 Convenções de Nomenclatura

- **Workflows**: `kebab-case` (ex: `email-automation.json`)
- **Categorias**: `kebab-case` (ex: `social-media/`)
- **Commits**: `conventional-commits` (ex: `feat: adiciona workflow`)
- **Branches**: `feature/nome-da-feature`

### 🎨 Padrões de Código

- **JSON**: Formatação consistente
- **Markdown**: Uso de emojis e estrutura clara
- **Comentários**: Em português
- **Variáveis**: Nomes descritivos

---

## 🚨 Reportando Problemas

### 🐛 Template de Bug Report

```markdown
## 🐛 Descrição do Bug

Descrição clara e concisa do problema.

## 🔄 Passos para Reproduzir

1. Vá para '...'
2. Clique em '...'
3. Role até '...'
4. Veja o erro

## ✅ Comportamento Esperado

O que deveria acontecer.

## 📸 Screenshots

Se aplicável, adicione screenshots.

## 💻 Ambiente

- **n8n**: versão
- **Sistema**: OS
- **Navegador**: versão

## 📋 Informações Adicionais

Qualquer contexto adicional.
```

### 💡 Template de Feature Request

```markdown
## 💡 Descrição da Feature

Descrição clara da funcionalidade desejada.

## 🎯 Problema que Resolve

Qual problema esta feature resolveria.

## 💭 Solução Proposta

Como você gostaria que funcionasse.

## 🔄 Alternativas Consideradas

Outras soluções que você considerou.

## 📋 Informações Adicionais

Contexto adicional, screenshots, etc.
```

---

## 🏆 Reconhecimento

### 🌟 Contribuidores

Contribuições significativas serão reconhecidas:

- **📝 Menção** no README
- **🏆 Badge** de contribuidor
- **📢 Divulgação** nas redes sociais
- **🎁 Acesso antecipado** a novas features

### 📊 Tipos de Contribuição

- **🥇 Ouro**: Workflows complexos e bem documentados
- **🥈 Prata**: Melhorias significativas
- **🥉 Bronze**: Correções e pequenas melhorias

---

## 📞 Suporte

### 💬 Comunidade

- **Discord**: [Link do servidor](https://discord.gg/exemplo)
- **Telegram**: [@n8n_automation](https://t.me/n8n_automation)
- **Email**: contribuicoes@exemplo.com

### 📚 Recursos

- **Documentação**: [docs.exemplo.com](https://docs.exemplo.com)
- **Tutoriais**: [tutorials.exemplo.com](https://tutorials.exemplo.com)
- **Exemplos**: [examples.exemplo.com](https://examples.exemplo.com)

---

## 📄 Licença

Ao contribuir, você concorda que suas contribuições serão licenciadas sob a mesma licença do projeto (MIT).

---

<div align="center">

**🤝 Obrigado por contribuir para a comunidade n8n!**

</div>
