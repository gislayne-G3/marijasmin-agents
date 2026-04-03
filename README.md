# Marijasmin Agents

Repositorio de skills/agents do ecossistema de IA da Marijasmin.

Cada arquivo .md define um agente especializado.
O conteudo do arquivo e usado como system prompt da Claude API.

## Estrutura

```
crm/
├── mari-sdr.md              <- Atendimento WhatsApp 24h
└── fiscal-crm.md            <- Monitor de metricas CRM

financeiro/
├── contador.md              <- Simples Nacional, DAS, NCM
├── fiscal.md                <- NFs, CFOP, ICMS
├── rh.md                    <- Comissoes, ferias, eSocial
├── juridico.md              <- CDC, LGPD, contratos
└── financeiro-estrategista.md <- DRE, dividas, projecao

marketing/
├── head-marketing.md        <- Maestro - distribui tarefas
├── analytics.md             <- Dados e metricas
├── gestor-trafego.md        <- Meta Ads, campanhas
├── email-marketing.md       <- Resend, segmentacao
├── social-media.md          <- IG, FB, TikTok metricas
├── copy.md                  <- Textos e campanhas
├── seo-blog.md              <- Google, conteudo organico
├── direct-comentarios.md    <- DMs e comentarios
├── video-motion.md          <- Roteiros e videos
├── designer-visual.md       <- DALL-E, criativos
├── influenciadoras.md       <- Parcerias e UGC
├── nps.md                   <- Satisfacao de clientes
├── reputacao.md             <- Comentarios e Reclame Aqui
├── prestadores.md           <- Fornecedores e parceiros
└── fiscal-marketing.md      <- Monitor do time de marketing

studio/
├── diretor-criativo.md      <- Visao criativa da colecao
├── pesquisador-tendencias.md <- Tendencias 2026
├── analista-vendas.md       <- O que vende mais e por que
├── especialista-tecidos.md  <- Tecidos e fornecedores
├── designer-visual.md       <- Prompts visuais e DALL-E
├── modelista-digital.md     <- Modelagem e caimento
└── curador-cristao.md       <- Alinhamento com valores cristaos
```

## Como usar

### No Next.js (Vercel)
```typescript
import { readFileSync } from 'fs'
import path from 'path'

const agentPath = path.join(process.cwd(), 'agents', `${agentId}.md`)
const systemPrompt = readFileSync(agentPath, 'utf-8')
```

### No n8n (Railway)
```
HTTP Request node:
URL: https://raw.githubusercontent.com/gislayne-G3/marijasmin-agents/main/[pasta]/[agente].md
Method: GET
Header: Authorization: token <GITHUB_PAT>
-> Output usado como system prompt no node Claude API
```

> Repositorio privado. Acesso via GitHub Personal Access Token.
