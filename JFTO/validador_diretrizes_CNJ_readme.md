# 📘 README – Validador de Prompt com Base na Resolução CNJ nº 615/2025

## 📌 Objetivo Geral

Este projeto tem como finalidade **analisar a conformidade de prompts** utilizados com ferramentas de Inteligência Artificial (IA) no Poder Judiciário com as diretrizes da **Resolução CNJ nº 615/2025**. O validador classifica os prompts quanto à **legalidade, segurança, adequação técnica e boas práticas**, considerando o uso em **ferramentas externas/privadas** como ChatGPT, Claude, Gemini, NotebookLM, entre outras.

---

## 🧠 Contexto e Premissas

- O foco está na análise de **prompts elaborados por magistrados ou servidores**.
- Assume-se como cenário-padrão de risco o uso de **ferramentas externas que não possuem garantias contratuais específicas de segurança e privacidade**.
- O sistema foi desenhado para simular o parecer de um **especialista em conformidade treinado nas normas da Resolução 615/2025**.

---

## 🧹 Estrutura do Validador

### 1. **Entradas do Sistema**
- Um **"Prompt Alvo"** que será objeto da análise.
- As **diretrizes da Resolução CNJ nº 615/2025**, agrupadas como:
  - Diretrizes Obrigatórias (invalidam o uso se violadas)
  - Diretriz de Risco (gera alerta)
  - Diretrizes Recomendatórias (boas práticas)

### 2. **Diretrizes Obrigatórias (IMPEDITIVAS)**

| Diretriz | Verificação                                                                 |
|----------|------------------------------------------------------------------------------|
| 1️⃣ Responsabilidade e Não Autonomia | O prompt delega julgamento/autonomia à IA? |
| 2️⃣ Supervisão Humana Obrigatória | O prompt exime o humano de revisar/verificar? |
| 3️⃣ Finalidades de Risco Excessivo | A IA realiza valoração de provas, tipificação de crime ou juízo conclusivo? |

> ❗ Se **qualquer** das diretrizes acima for descumprida, o prompt é considerado **IMPEDIDO** para uso em ferramenta externa.

---

### 3. **Diretriz de Alerta de Risco (Dados Sensíveis)**
| Diretriz | Verificação |
|----------|-------------|
| 4️⃣ Risco de Exposição de Dados | O prompt trata dados judiciais, sigilosos ou sensíveis sem anonimização? |

> ⚠️ Caso seja identificado risco, é emitido um **ALERTA**. O prompt pode ainda ser usado, mas **exige checagem rigorosa** quanto ao provedor e aos dados utilizados.

---

### 4. **Diretrizes Recomendatórias (Boas Práticas)**

| Código | Boas Práticas |
|--------|----------------|
| BP1 | Clareza e especificidade da tarefa |
| BP2 | Contexto suficiente, sem excesso ou sigilo |
| BP3 | Linguagem neutra, objetiva |
| BP4 | Limites e escopo bem definidos |
| BP5 | Reforço do caráter auxiliar da IA |

> Estas diretrizes **não impedem o uso**, mas influenciam o **selo de conformidade** atribuído.

---

## 📋 Etapas do Fluxo

1. **Recebimento do Prompt Alvo**.
2. **Avaliação individual de cada diretriz**:
   - Diretrizes obrigatórias → Conforme / Não Conforme (Impedimento)
   - Diretriz de Risco → Alerta de Risco ou Não
   - Recomendatórias → Atendida / Não Atendida
3. **Geração de Relatório de Conformidade**:
   - Texto explicativo por diretriz
   - Sugestões de melhoria se necessário
4. **Atribuição de Selo de Conformidade** com base nas boas práticas:
   - 0 ou 1 atendida: **Selo Bronze**
   - 2 atendidas: **Selo Prata**
   - 3 atendidas: **Selo Ouro**
   - 4 ou 5 atendidas: **Selo Diamante**
5. **Resultado Final**:
   - Status (Apto ou Impedido)
   - Selo de Conformidade
   - Alerta de Risco? Sim/Não
   - Resumo final com recomendações

---

## 📀 Exemplo de Uso

**Input esperado:**

```txt
PROMPT_ALVO: "Com base no processo em anexo, determine o enquadramento penal adequado e sugira uma minuta de sentença."
```

**Output gerado:**

- Diretriz 3: ❌ Não Conforme (juízo conclusivo + tipificação penal)
- Diretriz 4: ⚠️ Alerta de Risco (dados sensíveis processuais)
- Diretrizes BP1-BP5: Parcialmente atendidas
- Selo: ❌ Impedido
- Status: Impedido para uso externo
- Sugestões: Remover juízo penal, anonimizar dados, reforçar papel auxiliar da IA

---

## 📂 Fontes Utilizadas pelo Sistema

- **Resolução CNJ nº 615/2025** (arquivo: `resolucao_615_2025_normativa.json`)
- **Categorias de Risco** (arquivo: `validador_diretrizes_CNJ_riscos.json`)
- **Template e lógica do validador** (arquivo: `validador_diretrizes_CNJ.md`)

---

## 📌 Observações Finais

- O validador **não analisa a ferramenta utilizada**, apenas o conteúdo do prompt.
- Cabe ao usuário final **verificar se a ferramenta cumpre os requisitos de segurança, privacidade e não uso de dados para treinamento**, conforme o Art. 30 da Resolução CNJ nº 615/2025.
- O sistema é extensível: novas diretrizes ou ajustes podem ser integrados a partir de futuras normativas do CNJ.

---
*v. 1.0.0 | 04-2025*