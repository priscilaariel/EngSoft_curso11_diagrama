# Prompts utilizados

Registro dos prompts usados no discovery, seguindo o fluxo da Unidade III: primeiro lacunas e roteiro, depois o diagrama como código. A notação adotada é Mermaid.

## Prompt 1: lacunas e roteiro (estrutural)

```
Você é um arquiteto de software sênior. Antes de gerar qualquer diagrama,
identifique lacunas e faça perguntas de esclarecimento.

Descrição (linguagem natural):
<texto da seção 2 do README>

Objetivo do diagrama:
- Tipo: estrutural
- Nível: containers (inspirado no C4)
- Escopo: o agente, seu prompt, a interface de conversa, o repositório de
  desenhos e as integrações externas
- Fora do escopo: os fluxos que o agente desenha e as ferramentas desses fluxos

Restrições:
- Dependências proibidas: o agente não aciona as ferramentas dos fluxos
- O que não deve aparecer no diagrama: detalhes internos do modelo de linguagem

Entregue:
1) 5 a 10 lacunas ou ambiguidades relevantes.
2) 5 a 8 perguntas de esclarecimento, curtas e objetivas.
3) Um roteiro revisado em 8 a 12 linhas.

Regras: se faltar contexto, explicite; não assuma fatos.
Fora de escopo: não gere o diagrama nesta etapa.
```

## Prompt 2: diagrama de containers em Mermaid

```
Você é um arquiteto de software sênior. Gere um diagrama estrutural em Mermaid
a partir do roteiro revisado abaixo.

Roteiro revisado:
<roteiro>

Regras do diagrama:
- Use apenas o nível de containers; não misture níveis.
- Marque o modelo de linguagem e as ferramentas dos fluxos como sistemas externos.
- Mostre apenas dependências relevantes.
- Se algo for suposição, declare como suposição antes do código.

Entregue:
1) 3 a 6 suposições.
2) O código Mermaid completo em um bloco mermaid.
3) Um checklist de revisão de 8 a 12 itens, focado em estrutura e dependências.
```

## Prompt 3: diagrama de sequência da jornada crítica

```
Você é um arquiteto de software sênior. Gere um diagrama comportamental para
tornar explícitas as interações.

Descrição (linguagem natural):
Um usuário descreve um desafio novo de produção. O agente decompõe o processo
em etapas, classifica o nível de automação de cada uma, confere o ferramental
disponível e entrega o desenho do fluxo em 7 seções. O usuário revisa e, se o
desenho estiver adequado, arquiva. Se a descrição for insuficiente ou o desenho
precisar de ajuste, o comportamento esperado ainda não está totalmente decidido.

Objetivo do diagrama:
- Tipo: comportamental
- Notação: diagrama de sequência em Mermaid
- Escopo: jornada de pedido de desenho de fluxo, da descrição ao arquivamento

Entregue nesta ordem:
1) Lacunas e perguntas: 5 a 8 lacunas e 4 a 6 perguntas.
2) Roteiro revisado em 8 a 12 linhas, com participantes, mensagens relevantes,
   condição de sucesso e uma falha realista.
3) Mermaid: caminho de sucesso e caminho de falha. Indique onde a validação
   humana é obrigatória e por quê.
4) Checklist de 8 a 12 itens para revisão em pull request.

Regras: explicite suposições; não assuma fatos como certezas; não invente SLAs.
Fora de escopo: a execução dos fluxos desenhados.
```

## Observação

Os ajustes feitos sobre a saída do modelo estão registrados na seção 6 do README.
