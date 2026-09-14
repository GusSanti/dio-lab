# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Diversas pessoas tem dificuldades para controlar suas próprias finanças, fazendo investimentos de auto risco, e gerando gastos fúteis e desnecessários ao longo da vida.

### Solução
> Como o agente resolve esse problema de forma proativa?

Um modelo inteligente que irá auxiliar o usuário com dicas de investimento, e respondendo conceitos importantes na área de finanças baseadas no histórico financeiro do próprio usuário.

### Público-Alvo
> Quem vai usar esse agente?

Pessoas que necessitam de apoio com dicas financeiras e controle de gastos.

---

## Persona e Tom de Voz

### Nome do Agente
MatchCoin

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

Educativo e Paciente.
Age de forma respeitosa com o usuário.

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Informal e técnico

### Exemplos de Linguagem
- Saudação: "Olá, como podemos cuidar das suas finanças hoje?"
- Confirmação: "Certo! Me deixe verificar isso para você"
- Erro/Limitação: "No momento não tenho essa informação, porém vou te ajudar com uma coisa..."

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] -->|Mensagem| B[Interface]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | Streamlit |
| LLM | Ollama (local) |
| Base de Conhecimento | JSON/CSV |
| Validação | Checagem de alucinações |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] [Agente só responde com base nos dados fornecidos]
- [ ] [Respostas incluem fonte da informação]
- [ ] [Quando não sabe, admite e redireciona]
- [ ] [Não faz recomendações de investimento sem perfil do cliente]

### Limitações Declaradas
> O que o agente NÃO faz?

Não da informações enviesadas.
Não envia respostas alucinadas.
Não faz recomendações de investimento sem utilizar o perfil do cliente como base.
Não envia uma resposta sem fazer toda a checagem de segurança de dados e resposta.
