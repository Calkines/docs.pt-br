---
title: Número de registro inválido
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: abd0a1467c0991a40b93e74a1d7a7889367fb8ca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340796"
---
# <a name="bad-record-number"></a>Número de registro inválido
O número de registro em `a FileGet`, `FilePut`, `FileGetObject`, ou `FilePutObject` instrução é menor ou igual a zero.  
  
## <a name="to-correct-this-error"></a>Para corrigir este erro  
  
1. Verifique os cálculos usados para gerar o número do registro. Verifique a ortografia das variáveis que contém o número de registro ou usado no cálculo de números de registro. Um nome de variável digitado incorretamente é implicitamente declarado e inicializado como zero, a menos que você usou `Option Explicit On` no módulo.  
  
## <a name="see-also"></a>Consulte também

- [Instrução Option Explicit](../../visual-basic/language-reference/statements/option-explicit-statement.md)
