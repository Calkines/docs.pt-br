---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803190"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>A propriedade CheckForOverflowUnderflow do WinForm agora é true para System.Drawing

|   |   |
|---|---|
|Detalhes|A propriedade CheckForOverflowUnderflow do o assembly System.Drawing.dll está definida como true.|
|Sugestão|Anteriormente, quando os estouros ocorriam, o resultado teria sido truncado silenciosamente. Agora, uma exceção <xref:System.OverflowException?displayProperty=name> é gerada.|
|Escopo|Microsoft Edge|
|Versão|4.5|
|Tipo|Tempo de execução|
