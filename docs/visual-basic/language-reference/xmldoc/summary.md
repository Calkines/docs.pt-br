---
title: <summary> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 0fbe07884f55b7e6f460929e54520de5f718e1af
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814989"
---
# <a name="summary-visual-basic"></a>\<Resumo > (Visual Basic)
Especifica o resumo do membro.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a>Parâmetros  
 `description`  
 Um resumo do objeto.  
  
## <a name="remarks"></a>Comentários  
 Use o `<summary>` marca para descrever um tipo ou membro de tipo. Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) para adicionar mais informações a uma descrição de tipo.  
  
 O texto para o `<summary>` marca é a única fonte de informações sobre o tipo no IntelliSense e também é exibida no Pesquisador de objetos. Para obter informações sobre o Pesquisador de objetos, consulte [exibindo a estrutura do código](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Compile com [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para processar comentários de documentação em um arquivo.  
  
## <a name="example"></a>Exemplo  
 Este exemplo usa o `<summary>` marca para descrever o `ResetCounter` método e `Counter` propriedade.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Consulte também

- [Marcações de Comentário XML](../../../visual-basic/language-reference/xmldoc/index.md)
