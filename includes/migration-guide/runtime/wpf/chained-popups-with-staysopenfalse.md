---
ms.openlocfilehash: 22c4b61b293ac2366cae1dc73e0f6805a4a5fb8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803178"
---
### <a name="chained-popups-with-staysopenfalse"></a>Pop-ups encadeados com StaysOpen=False

|   |   |
|---|---|
|Detalhes|Um pop-up com StaysOpen=False deve fechar quando você clica fora dele. Quando dois ou mais pop-ups do tipo estão encadeados (por exemplo, quando um contém o outro), há muitos problemas, incluindo:<ul><li>Abra dois níveis, clique fora do P2, mas dentro do P1.  Nada acontecerá.</li><li>Abra dois níveis, clique fora do P1.  Ambos pop-ups serão fechados.</li><li>Abra e feche dois níveis.  Em seguida, tente abrir novamente o P2.  Nada acontecerá.</li><li>Tente abrir três níveis.  Não é possível fazer isso.  Nada acontecerá ou os primeiros dois níveis fecharão, dependendo de onde você clicar. Agora, esses casos (e outras variantes) funcionam conforme o esperado.</li></ul>|
|Escopo|Microsoft Edge|
|Versão|4.7.1|
|Tipo|Tempo de execução|
|APIs afetadas|<ul><li><xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType></li></ul>|
