---
title: 'Como: Localizar um atributo do pai (XPath-LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 9d2572fd-27d4-426c-b079-16854cb9ec7d
ms.openlocfilehash: ded20c173063492d260aee5ba55f3c4c585bd961
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828648"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-visual-basic"></a>Como: Localizar um atributo do pai (XPath-LINQ to XML) (Visual Basic)
Este tópico mostra como navegar para o elemento pai e localizar um atributo deles.  
  
 A expressão XPath é:  
  
 `../@id`  
  
## <a name="example"></a>Exemplo  
 Este exemplo localiza primeiro um elemento de `Author` . Localiza no atributo de `id` de elemento pai.  
  
 Este exemplo usa o seguinte documento XML: [Arquivo XML de exemplo: Livros (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
```vb  
Dim books As XDocument = XDocument.Load("Books.xml")  
Dim author As XElement = books.Root.<Book>.<Author>.FirstOrDefault()  
  
' LINQ to XML query  
Dim att1 As XAttribute = author.Parent.Attribute("id")  
  
' XPath expression  
Dim att2 As XAttribute = DirectCast(author.XPathEvaluate("../@id"),  _  
    IEnumerable).Cast(Of XAttribute)().First()  
  
If att1 Is att2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(att1)  
```  
  
 Este exemplo gera a seguinte saída:  
  
```  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a>Consulte também

- [LINQ to XML para os usuários do XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
