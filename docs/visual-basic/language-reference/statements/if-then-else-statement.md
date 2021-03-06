---
title: Instrução If...Then... (Visual Basic)
ms.date: 04/16/2018
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
ms.openlocfilehash: d91a913d515f36a6b974850bc30079b000a919b4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842688"
---
# <a name="ifthenelse-statement-visual-basic"></a>Instrução If...Then... (Visual Basic)
Execute um grupo de instruções condicionalmente, dependendo do valor de uma expressão.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
' Multiline syntax:  
If condition [ Then ]  
    [ statements ]  
[ ElseIf elseifcondition [ Then ]  
    [ elseifstatements ] ]  
[ Else  
    [ elsestatements ] ]  
End If  
  
' Single-line syntax:  
If condition Then [ statements ] [ Else [ elsestatements ] ]  
```  

## <a name="quick-links-to-example-code"></a>Links rápidos para código de exemplo

Este artigo inclui vários exemplos que ilustram usos do `If`... `Then`... `Else` instrução:

* [Exemplo de sintaxe de várias linhas](#multi-line)
* [Exemplo de sintaxe aninhados](#nested)
* [Exemplo de sintaxe de linha única](#single-line)

## <a name="parts"></a>Partes  
 `condition`  
 Necessário. expressão. Deve ser avaliada como `True` ou `False`, ou para um tipo de dados que é implicitamente conversível para `Boolean`.  
  
 Se a expressão for um [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variável que é avaliada como [nada](../../../visual-basic/language-reference/nothing.md), a condição será tratada como se a expressão é `False` e o `Else` bloco é executado.  
  
 `Then`  
 Obrigatório na sintaxe de linha única; opcional na sintaxe de várias linhas.  
  
 `statements`  
 Opcional. Um ou mais instruções após `If`... `Then` que são executadas se `condition` é avaliada como `True`.  
  
 `elseifcondition`  
 Necessário se `ElseIf` está presente. expressão. Deve ser avaliada como `True` ou `False`, ou para um tipo de dados que é implicitamente conversível para `Boolean`.  
  
 `elseifstatements`  
 Opcional. Um ou mais instruções após `ElseIf`... `Then` que são executadas se `elseifcondition` é avaliada como `True`.  
  
 `elsestatements`  
 Opcional. Uma ou mais instruções que são executadas se não anterior `condition` ou `elseifcondition` expressão é avaliada como `True`.  
  
 `End If`  
 Encerra a versão multilinha do `If`... `Then`... `Else` bloco.  
  
## <a name="remarks"></a>Comentários  
  
### <a name="multiline-syntax"></a>Sintaxe de várias linhas  
 Quando um `If`... `Then`... `Else` instrução for encontrada, `condition` é testada. Se `condition` está `True`, as instruções a seguir `Then` são executadas. Se `condition` está `False`, cada `ElseIf` instrução (se houver) é avaliada na ordem. Quando um `True` `elseifcondition` for encontrado, as instruções imediatamente após associado `ElseIf` são executadas. Se nenhum `elseifcondition` for avaliada como `True`, ou se não houver nenhum `ElseIf` instruções, as instruções a seguir `Else` são executadas. Depois de executar as seguintes instruções `Then`, `ElseIf`, ou `Else`, a execução continua com a instrução após `End If`.  
  
 O `ElseIf` e `Else` cláusulas são opcionais. Você pode ter tantos `ElseIf` cláusulas como você deseja em um `If`... `Then`... `Else` instrução, mas não `ElseIf` cláusula pode aparecer após um `Else` cláusula. `If`... `Then`... `Else` instruções podem ser aninhadas dentro uns dos outros.  
  
 Na sintaxe de várias linhas, o `If` instrução deve ser a única instrução na primeira linha. O `ElseIf`, `Else`, e `End If` instruções podem ser precedidas apenas por um rótulo de linha. O `If`... `Then`... `Else` bloco deve terminar com um `End If` instrução.  
  
> [!TIP]
>  O [selecione... Instrução de caso](../../../visual-basic/language-reference/statements/select-case-statement.md) pode ser mais útil quando você avalia uma única expressão que tem vários valores possíveis.  
  
### <a name="single-line-syntax"></a>Sintaxe de linha única  
 Você pode usar a sintaxe de linha única para uma única condição com o código a ser executado se for true. No entanto, a sintaxe de várias linhas fornece mais estrutura e a flexibilidade e é mais fácil de ler, manter e depurar.  
  
 O que segue o `Then` palavra-chave é examinado para determinar se uma instrução é uma única linha `If`. Se algo diferente de um comentário aparece depois `Then` na mesma linha, a instrução é tratada como uma única linha `If` instrução. Se `Then` estiver ausente, ele deve ser o início de várias linhas `If`... `Then`... `Else`.  
  
 Na sintaxe de linha única, você pode ter várias declarações executadas como o resultado de uma `If`... `Then` decisão. Todas as instruções devem estar na mesma linha e ser separadas por dois-pontos.  

## <a name="multiline-syntax-example"></a>Exemplo de sintaxe de várias linhas

<a name="multi-line"></a>
 
 O exemplo a seguir ilustra o uso da sintaxe de várias linhas de `If`... `Then`... `Else` instrução.  
  
 [!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>Exemplo de sintaxe aninhados

<a name="nested"></a>

 O exemplo a seguir contém aninhada `If`... `Then`... `Else` instruções.  
  
 [!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a>Exemplo de sintaxe de linha única
  
<a name="single-line"></a> O exemplo a seguir ilustra o uso da sintaxe de linha única.  
  
 [!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]
  
## <a name="see-also"></a>Consulte também

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [Diretivas #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Instrução Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [Estruturas de Controle Aninhadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Estruturas de Decisão](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Operadores lógicos e bit a bit no Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Operador If](../../../visual-basic/language-reference/operators/if-operator.md)
