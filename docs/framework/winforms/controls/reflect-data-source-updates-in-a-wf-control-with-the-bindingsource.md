---
title: 'Como: Refletir atualizações feitas na fonte de dados em um controle do Windows Forms com o BindingSource'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], updating
- BindingSource component [Windows Forms], updating data binding
- examples [Windows Forms], BindingSource component
- data sources [Windows Forms], updating
- BindingSource component [Windows Forms], examples
ms.assetid: bd8bd9b2-af8a-4f11-a3d5-54eecbe2400b
ms.openlocfilehash: 16dbe4da1efecd120d4da4d66c3d79ec907b92a6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218636"
---
# <a name="how-to-reflect-data-source-updates-in-a-windows-forms-control-with-the-bindingsource"></a>Como: Refletir atualizações feitas na fonte de dados em um controle do Windows Forms com o BindingSource
Quando você usa controles ligados a dados, às vezes, você precisa responder a alterações na fonte de dados quando a fonte de dados não gera eventos de alteração de lista. Quando você usa o <xref:System.Windows.Forms.BindingSource> componente para associar a fonte de dados a um controle Windows Forms, você pode notificar o controle que sua fonte de dados foi alterado, chamando o <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> método.  
  
## <a name="example"></a>Exemplo  
 O exemplo de código a seguir demonstra como usar o <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> método para notificar um controle associado sobre uma atualização na fonte de dados.  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Este exemplo requer:  
  
-   Referências aos assemblies System, System.Drawing e System.Windows.Forms.  
  
 Para obter informações sobre como compilar este exemplo da linha de comando para o Visual Basic ou Visual c#, consulte [compilando da linha de comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) ou [criação de linha de comando com csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Você também pode criar este exemplo no Visual Studio colando o código em um novo projeto.  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Componente BindingSource](bindingsource-component.md)
- [Como: Associar um controle dos Windows Forms a um tipo](how-to-bind-a-windows-forms-control-to-a-type.md)
