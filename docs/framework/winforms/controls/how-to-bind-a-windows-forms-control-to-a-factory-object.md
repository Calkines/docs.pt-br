---
title: 'Como: Associar um controle do Windows Forms a um objeto de alocador'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], binding
- factory objects [Windows Forms], binding to
- BindingSource component [Windows Forms], binding to a factory object
- BindingSource component [Windows Forms], examples
ms.assetid: 7d59af89-ff82-41d8-a48a-f1fbae788b0d
ms.openlocfilehash: 2de892d94afdfcdc580d20f90fb60ebabf4a9b37
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093027"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-factory-object"></a>Como: Associar um controle do Windows Forms a um objeto de alocador
Quando você estiver criando controles que interagem com os dados, às vezes, será necessário associar um controle a um objeto ou método que gere outros objetos. Esse objeto ou método é chamado de alocador. A fonte de dados pode ser, por exemplo, o valor retornado de uma chamada de método, em vez de um objeto na memória ou um tipo. Você pode associar um controle a esse tipo de fonte de dados desde que a fonte retorne uma coleção.  
  
 Você pode associar facilmente um controle para um objeto de fábrica usando o <xref:System.Windows.Forms.BindingSource> controle.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir demonstra como associar um <xref:System.Windows.Forms.DataGridView> controle para um método de fábrica usando um <xref:System.Windows.Forms.BindingSource> controle. O método de fábrica chama-se `GetOrdersByCustomerId` e retorna todos os pedidos para determinado cliente no banco de dados Northwind.  
  
 [!code-cpp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Este exemplo requer:  
  
-   Referências aos assemblies System, System.Data, System.Drawing e System.Windows.Forms.  
  
 Para obter informações sobre como compilar este exemplo da linha de comando para o Visual Basic ou Visual c#, consulte [compilando da linha de comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) ou [criação de linha de comando com csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Você também pode criar este exemplo no Visual Studio colando o código em um novo projeto.  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Componente BindingSource](bindingsource-component.md)
- [Como: Associar um controle dos Windows Forms a um tipo](how-to-bind-a-windows-forms-control-to-a-type.md)
