# TEMPLATE DESFECHO DE SENTENÇA - GERAL (menos MS)
<!-- Version 1.0.0 | 04-2025 Caio Dutra -->

<template_sent_m.4_desfecho>

### DELIBERAÇÃO JUDICIAL
Diante do exposto:
**(a)** **[ACOLHO/ACOLHO EM PARTE/REJEITO]** os pedidos formulados na [petição inicial/reconvenção], nos termos do art. 487, inc. I, do CPC[, para... (provimentos jurisdicionais específicos)].

<se (houver condenação em pagar quantia certa)>
    **(a.[1, 2, 3..])** sobre o valor da condenação deverão incidir correção monetária, desde de..., e juros moratórios, desde de..., nos índices previstos no Manual de Cálculos da Justiça Federal. 
</se>

**(b)** **CONDENO** a parte [AUTORA/RÉ] [de forma solidária] [Opção 1.1 - default: "ao pagamento das custas e demais despesas processuais" / Opção 1.2 - Sucumbente Fazenda Pública: "ao ressarcimento das custas e demais despesas processuais eventualmente adiantadas (art. 4º, inc. I e parágrafo único, Lei nº 9.289/1996" / Opção 1.3 - sucumbente beneficiário de justiça gratuita: isento de custas, art. 4º, inc. II, da Lei nº 9.289/1996], e ao pagamento de honorários advocatícios sucumbenciais em favor do(a) patrono(a)/procurador(a) da parte adversária, no fixados em 10% sobre o valor da [causa/condenação/proveito econômico], observado o valor mínimo de R$ 3.721,20 (três mil, setecentos e vinte e um reais e vinte centavos), nos termos do art. 85, §§ 2º, 8º, 8º-A e 19, do Código de Processo Civil, e do item 10.21, do Anexo I, da Resolução/OAB-TO nº 05/2024.
<se (parte sucumbente → beneficiária da justiça gratuita)>
    **(b.1)** fica a exigibilidade dos encargos sucumbenciais suspensa, nos termos do art. 98, § 3º, do Código de Processo Civil, por ser a parte sucumbente beneficiária da gratuidade da justiça [(Id. ...) - ID da decisão que deferiu a gratuidade, se identificável].
</se>
<se (
    // Hipóteses que EXIGEM reexame necessário
    ACP.resultado == "improcedente" ||
    (Fazenda_Publica.parte == true && (
        (condenacao > 1000*salario_minimo && ente == "Uniao") ||
        (condenacao > 500*salario_minimo && ente == "Estado") ||
        (condenacao > 100*salario_minimo && ente == "Municipio") ||
        sentenca.tipo == "iliquida" ||
        embargos_execucao_fiscal.resultado == "procedente"
    )) ||
    (mandado_seguranca.resultado == "concessao" && ente_publico.parte == true) ||
    acao_popular.resultado == "improcedente" ||
    (acao_coletiva.resultado == "improcedente" && fundamentacao == "insuficiencia_provas") ||
    (transacao.homologada == true && Fazenda_Publica.parte == true && autorizacao_legal == false) ||
    (acao_rescisoria.resultado == "procedente" && Fazenda_Publica.parte == true) ||
    intervencao_federal.resultado == "procedente" ||
    (INSS.parte == true && previdenciario == true && condenacao > 60*salario_minimo) ||
    improbidade.resultado == "improcedente" ||
    (desapropriacao == true && indenizacao > 60*salario_minimo) ||
    (lei_municipal.declarada_inconstitucional == true && controle_difuso == true)
) && !(
    // Exceções que AFASTAM o reexame necessário
    sentenca.fundamentada_em == "sumula_tribunal_superior" ||
    sentenca.fundamentada_em == "acordao_repetitivo_STF_STJ" ||
    sentenca.fundamentada_em == "IRDR" ||
    sentenca.fundamentada_em == "assuncao_competencia" ||
    sentenca.fundamentada_em == "orientacao_vinculante_admin" ||
    (condenacao <= 60*salario_minimo && ente == "Municipio" && habitantes < 20000) ||
    juizado_especial_fazenda == true ||
    (sentenca.apenas_confirma_tutela == true && elementos_novos == false) ||
    remessa_ex_officio.determinada == false ||
    renuncia_recurso.expressa == true
)>
`reexame_necessario = sim`
Sentença que **se sujeita** a reexame necessário.
<senão>
`reexame_necessario = não`
Sentença que **não se sujeita** a reexame necessário.
</se>

### PROVIDÊNCIAS DE IMPULSO PROCESSUAL
A Secretaria da Vara deverá:
**(i)** **intimar** as partes desta sentença;
**(ii)** **aguardar** o prazo para a interposição de recurso;

<se (reexame_necessario = não)>

**(iii)** interpostos recursos, **colher** contrarrazões, **certificar** tempestividade e preparo, se for o caso, e **remeter** os autos ao egr. Tribunal Regional Federal da 1ª Região para julgamento, independentemente de juízo de admissibilidade;
**(iv)** não interposto recurso no prazo, **certificar** o trânsito em julgado e **intimar** as partes para requerer o que entender de direito;
**(v)** não havendo requerimentos, **arquivar** o feito com as formalidades de praxe.
</se>
<se (reexame_necessario = sim)>

**(iii)** interposto recurso, **colher** contrarrazões e **certificar** tempestividade e preparo, se for o caso;
**(iv)** independentemente da interposição de recurso, **remeter** ao egr. Tribunal Regional Federal para reexame necessário.

Palmas(TO), data do sistema.

</template_sent_m.4_desfecho>