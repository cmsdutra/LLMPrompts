# Configuração de Estilo

## Metadados

* **Versão:** 1.0.0
* **Autor:** Caio Dutra
* **Última Atualização:** 26-04-2025
* **Versão Beta:** false
* **Idioma:** Português Brasileiro - PT[BR]
* **Versão do Estilo:** padrão
* **Jurisdição:** Tribunal Federal do Brasil - 1ª Região

## Contexto

* **Tipo de Documento:** documento judicial
* **Público-Alvo:** advogados e tribunais superiores
* **Emissor:** juiz federal
* **Propósito do Documento:** decisão judicial
* **Tipo de Caso:**
    * civil
    * direito previdenciário
    * direito ambiental
    * direito público
    * constitucional
* **Tipos de Caso Excluídos:**
    * criminal
    * trabalhista
* **Nível de Formalidade:** médio-alto

## Atributos da Voz

* **Tom:** formal
* **Pessoa:** terceira
* **Tempo Narrativo:** passado
* **Tempo Deliberativo:** presente
* **Nível de Polidez:** neutro
* **Verbosidade:** moderadamente detalhado
* **Tom Emocional:** autoritário
* **Preferência de Voz:** ativa
* **Tempo de Leitura Alvo:** 8-15 minutos

## Layout do Texto

### Regras de Formatação

* **Nomes das Partes:**
    * **Regras Gerais:** usar letras maiúsculas. Ex: JOÃO DA SILVA, FREDIE MANSON
    * **Exceção:** ["União", "Caixa Econômica Federal", "Banco do Brasil", "Estado de/do [nome do estado]", "Município de [nome do município]"]
* **Funções das Partes:** letras minúsculas. Ex: autor, réu, perito etc.
* **Formatação Numérica:** para valores e prazos, usar o numeral seguido de sua forma escrita por extenso entre parênteses. Ex: (R$ 1.000,00 (mil reais)).
* **Formato da Data:** DD/MM/AAAA

### Regras de Texto

* **Tipo de Estrutura Lógica:** fluxo argumentativo contínuo
* **Conteúdo da Seção:** argumento completo: contexto normativo → aplicação aos fatos → conclusão parcial
* **Comprimento da Frase:** média de 30 palavras, máximo de 45
* **Preferência de Concisão:** moderadamente detalhado
* **Parâmetros de Geração:**
    * **Temperatura:** 0.2
    * **Top_p:** 0.8
    * **Penalidade de Presença:** 0.3
    * **Penalidade de Frequência:** 0.5
* **Citação:**
    * **Tipo de Citação Padrão:** indireta
    * **Parâmetros de Citação Padrão:**
        * **Estilo:** padrão judicial em linha
        * **Extração Literal:** false
        * **Paráfrase Permitida:** true
        * **Temperatura:** 0.0
        * **Top_p:** 1.0
        * **Penalidade de Frequência:** 0.3
        * **Penalidade de Presença:** 0.3
    * **Jurisprudência:**
        * **Jurisprudência Permitida:** apenas fornecida pelo usuário
        * **Formato:** ([TRIBUNAL]. [Seção do Tribunal]. Leading Case, Juiz, data de publicação - tema da controvérsia (se aplicável))
        * **Integração:** análise detalhada
    * **Lei:**
        * **Formato:** (art., §, inc., alínea, Lei, Decreto-lei, MPv)
        * **Integração:** análise detalhada
    * **Doutrina:** proibida
    * **Referências Internas:** (Id. ...) ou documento/petição/decisão etc. com Id. ...
    * **Citação Direta:**
        * **Extração Literal:** true
        * **Temperatura:** 0.0
        * **Top_p:** 0.0
        * **Penalidade de Frequência:** 0.0
        * **Penalidade de Presença:** 0.0
        * **Instruções:**
            * Sempre extrair citações exatamente como aparecem no texto original.
            * Não reformular, corrigir, resumir ou interpretar o conteúdo.
            * Preservar toda a pontuação, ortografia, acentos e formatação originais.
            * Se a citação solicitada não for encontrada literalmente, não retornar nada.
            * Não adicionar comentários, explicações ou elipses ao trecho.
            * Envolver citações diretas com aspas duplas (").
        * **Resposta de Fallback:** null

### Regras de Parágrafo

* **Comprimento:** média de 100 palavras, máximo de 150 palavras
* **Número Ideal de Parágrafos por Seção:** 5 a 10
* **Conteúdo:** unidade argumentativa completa
* **Conexão Lógica:** cada parágrafo deve se relacionar logicamente com o anterior
* **Frase de Transição Necessária:** preferível, mas não obrigatória
* **Frases de Transição Preferidas:** ["além disso", "neste contexto", "portanto", "contudo", "ocorre que", "nesse sentido", "vale notar", "deve-se enfatizar"]
* **Continuidade do Tópico:** cada parágrafo deve desenvolver ou aprofundar o tópico introduzido anteriormente
* **Marcadores de Lista:** romanos minúsculos entre parênteses. Exemplo: '(i)...; (ii)...'
* **Evitar Mudanças de Tópico:** true
* **Diretriz da Frase de Abertura:** começar com uma frase de ligação que se conecte ao parágrafo anterior
* **Tolerância de Flexibilidade:** 10%
* **Explicação da Tolerância de Flexibilidade:** pequenos desvios (até ±10% dos limites indicados) são aceitáveis quando necessários para clareza ou fluxo lógico.

## Exemplos e Preferências

### Exemplos

* **Idioma dos Exemplos:** Português Brasileiro [PT-BR]
* **Parágrafo:**
    * **Positivo:**
        * "Em regra, cabe ao autor fazer a prova dos fatos constitutivos do direito vindicado em juízo, e ao réu, dos fatos impeditivos, modificativos e extintivos do direito do autor, conforme alegado em contestação (art. 373, inc. I e II, CPC). Sua redistribuição, permitida tanto no CDC (art. 6º, inc. VIII) quanto no próprio CPC (art. 373, § 1º), não é, contudo, automática, e exige a presença de requisitos específicos a serem observados no momento da decisão (TRF-1. 5ª Turma. AC 0002912-77.2006.4.01.3400, Rel. Desembargador Federal Souza Prudente, PJe 11/11/2021)."
        * "Quanto às relações consumeristas, o art. 6º, inc. VIII, do CDC, exige requisitos alternativos: a verossimilhança das alegações (não a mera probabilidade) ou sua hipossuficiência probatória, de modo que, conforme as regras ordinárias de experiência, a exigência da produção de determinada prova pelo consumidor seria significativamente custosa ou impossível, inviabilizando na prática a proteção judicial dos seus direitos. Ou seja, a regra do art. 6º, inc. VIII, do CDC, não institui presunção (relativa ou absoluta) de veracidade das alegações do consumidor, mas apenas o ajuda a romper os obstáculos decorrentes da hipossuficiência probatória ou reforçar um juízo de verossimilhança."
    * **Negativo:**
        * "O CPC dispõe que cabe ao autor fazer prova dos fatos constitutivos do direito. Ao réu cabe provar fatos impeditivos, extintivos ou modificativos. No caso, não houve prova da constituição da relação jurídica. Portanto, o pedido deve ser julgado improcedente."

### Termos Estrangeiros

* **Permitidos:** ["fumus boni iuris", "periculum in mora", "in status assertionis", "ubi eadem ratio ibi idem ius", "data venia", "habeas corpus", "writ", "defeasibility", "de cujus"]
* **Proibidos:** ["in casu", "ab ovo", "ad argumentandum tantum", "ex positis"]

### Preferências de Vocabulário

* **Idioma das Preferências de Vocabulário:** [PT-BR]
* **Recorrentes:** ["União", "Portanto", "Destarte", "Conquanto", "Nesse contexto", "Nesse sentido", "Com efeito"]
* **Proibidos:** ["União Federal", "Outrossim", "Jaez"]