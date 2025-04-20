# SF 1.2 - Extração de dados gerais

## Objetivo
Extrair os dados estruturais e cadastrais principais do processo, bem como a qualificação das partes e representantes. Essa extração serve como base para organização dos metadados do processo judicial.
## Instruções
### Formato da Resposta
Ao executar o fluxo, apresente a resposta no próprio chat (não use canvas) em formato .json, utilizando a estrutura a seguir

```json
{
  "dados_gerais": {
    "numero_processo": "",
    "tipo_acao": "",
    "data_protocolo": "",
    "juizo": "",
    "valor_causa": "",
    "segredo_justica": "",
    "gratuidade_justica": "",
    "prioridade": "",
    "assunto": {
      "ramo_direito": "",
      "materia": ""
    },
    "data_ultima_peca": "",
    "tipo_minuta": ""
  },
  "partes_e_procuradores": {
    "autor": [
      {
        "nome": "",
        "representantes": [] ,
        "advogados": []
      }
    ],
    "reus": [
      {
        "nome": "",
        "representantes": [],
        "advogados": []
      }
    ],
    "terceiros": [
      {
        "nome": "",
        "tipo_intervencao": "",
        "advogados": [""]
      }
    ]
  }
}
```
#### Etapas de execução
Execute o fluxo descrito abaixo:
1. Extraia e registre os seguintes campos no bloco `dados_gerais`:    
    -  `numero_processo`
    - `tipo_acao` (procedimento comum, JEF, especial etc.)
    - `data_protocolo`
    - `juizo`
    - `valor_causa`
    - `segredo_justica` (não pedido, concedido, negado, revogado)
    - `gratuidade_justica`
    - `prioridade`
    - `assunto.ramo_direito`
    - `assunto.materia`
    - `data_ultima_peca` (com base cronológica nos documentos recebidos)
    - `tipo_minuta` (valor já fornecido na etapa anterior)        
2. Extraia e registre os dados das partes e representantes no bloco `partes_e_procuradores`: 
    - Para cada autor, réu e terceiro:
    - `nome`
    - `representantes` (se houver)
    - `advogados`
    - Para terceiros, inclua também o campo `tipo_intervencao`            
3. Se algum campo estiver ausente ou incompleto:
    - Preencha com `null` ou `"não informado"`

## Esclarecimentos
**Atenção:**
- Não invente dados, nem faça interpretações; 
- Se não for possível identificar o campo no arquivo apresentado, indique no valor a impossibilidade.
