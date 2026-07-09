# Quiz — House Premium Residence

Quiz de qualificação de leads, mobile-first, para o lançamento House Premium Residence (CS Empreendimentos, Santarém-PA).

Arquivo único e autocontido: [`index.html`](index.html) — a logo está embutida em base64, as fontes (Baskervville + Inter) e as bibliotecas de animação (GSAP + canvas-confetti) carregam via CDN.

## Fluxo

Intro → 4 perguntas de qualificação (renda, entrada, financiamento, prazo) → análise animada → captura de nome + WhatsApp → tela de sucesso com confetti e botão para o WhatsApp do consultor com as respostas pré-preenchidas.

## Configuração

No topo do `<script>` em `index.html`:

```js
const CONFIG = {
  whatsappNumber: "5593999999999", // número do consultor (DDI 55 + DDD + número)
  webhookUrl: "https://editor.leaderaperformance.com.br/webhook/house-premium"
};
```

O lead é enviado ao webhook em JSON:

```json
{
  "nome": "...",
  "whatsapp": "5593...",
  "respostas": { "renda": "...", "entrada": "...", "financiamento": "...", "prazo": "..." },
  "origem": "quiz-house-premium",
  "data": "ISO 8601"
}
```

## Rodar localmente

```bash
python3 -m http.server 4173
# abra http://localhost:4173
```
