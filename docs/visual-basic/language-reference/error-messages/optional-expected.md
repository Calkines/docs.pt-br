---
title: "'Optional' esperado"
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 71a25784f357a7e596093b314ed5b3d721d6f92c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59341875"
---
# <a name="optional-expected"></a>'Optional' esperado
Um argumento opcional em uma declaração de procedimento é seguido por um argumento obrigatório. Cada argumento após um argumento opcional também deve ser opcional.  
  
 **ID do erro:** BC30202  
  
## <a name="to-correct-this-error"></a>Para corrigir este erro  
  
1. Se o argumento deve ser necessária, movê-la para preceder o primeiro argumento opcional na lista de argumentos.  
  
2. Se o argumento deve ser opcional, use o `Optional` palavra-chave.  
  
## <a name="see-also"></a>Consulte também

- [Parâmetros Opcionais](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
