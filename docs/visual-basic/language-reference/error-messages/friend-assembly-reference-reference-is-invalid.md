---
title: A referência de assembly amigável <reference> é inválida.
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 0c1526e32ddc64cb4124c6f8205d58deef911dd6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59298988"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>Referência de assembly Friend \<referência > é inválido
Referência de assembly Friend \<referência > é inválido. O nome forte assinado em assemblies deve especificar uma chave pública em suas declarações InternalsVisibleTo.  
  
 O nome do assembly passado para o <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> construtor de atributo identifica um assembly de nome forte, mas ele não inclui um `PublicKey` atributo.  
  
 **ID do erro:** BC31535  
  
## <a name="to-correct-this-error"></a>Para corrigir este erro  
  
1. Determine a chave pública para o assembly de nome forte amigo. Incluir a chave pública como parte do nome do assembly passado para o <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> construtor de atributo usando o `PublicKey` atributo.  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Reflection.AssemblyName>
- [Assemblies Amigáveis](../../../standard/assembly/friend-assemblies.md)
