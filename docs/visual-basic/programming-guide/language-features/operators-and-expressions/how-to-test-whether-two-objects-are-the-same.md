---
title: 'Como: Testar se dois objetos são o mesmo (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: dbb268175d197e7b931af45a98f3a273c593e5a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819098"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>Como: Testar se dois objetos são o mesmo (Visual Basic)
Se você tiver duas variáveis se referirem a objetos, você pode usar o `Is` ou `IsNot` operador, ou ambos, para determinar se eles se referem à mesma instância.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>Para testar se dois objetos são iguais  
  
-   Use o [operador Is](../../../../visual-basic/language-reference/operators/is-operator.md) ou o [operador IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) com as duas variáveis como operandos.  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 Você talvez queira levar a uma determinada ação, dependendo se os dois objetos se referirem à mesma instância. O exemplo anterior compara o controle `c` contra o controle ativo no formulário `f`. Se não há nenhum controle ativo, ou se não houver um, mas isso não é a mesma instância de controle que `c`, em seguida, a `If` instrução falhará e o procedimento retornará sem processamento adicional.  
  
 Se você usar `Is` ou `IsNot` é uma questão de conveniência pessoal para você. Um pode ser mais fácil de ler que o outro em uma expressão fornecida.  
  
## <a name="see-also"></a>Consulte também

- [Operadores de comparação no Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
