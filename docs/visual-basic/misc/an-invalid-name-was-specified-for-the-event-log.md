---
title: Um nome inválido foi especificado para o log de eventos
ms.date: 07/20/2015
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
ms.openlocfilehash: 2b9c934272d0f3392c845dcd2f0062a98dc50c7b
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58032262"
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a>Um nome inválido foi especificado para o log de eventos
Um nome inválido foi especificado para o log de eventos. Normalmente, este é um resultado de caracteres inválidos no nome da, um nome de arquivo em branco ou um nome de arquivo é muito longo.  
  
## <a name="to-correct-this-error"></a>Para corrigir este erro  
  
-   Se o nome especificado é a mais de oito caracteres, verifique se que há nenhum conflito com os nomes dos outros logs de eventos. Somente os oito primeiros caracteres são avaliados para determinar se o nome é exclusivo.  
  
-   Se você estiver fornecendo um caminho, certifique-se de que ele é analisado corretamente.  
  
-   Verifique não se há nenhum caractere inválido no nome. Caracteres que não podem ser usados em um nome de arquivo incluem `<`, `>`, `:`, `"`, `/`, `\`, e `|`.  
  
## <a name="see-also"></a>Consulte também

- [Como: Analisar caminhos de arquivo](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
- [Como: Renomear um arquivo](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
