---
title: 'Como: Tornar um controle TextBox somente leitura'
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 7f24458eb98bd669d59f15c49d1d9e3beb6833b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229830"
---
# <a name="how-to-make-a-textbox-control-read-only"></a>Como: Tornar um controle TextBox somente leitura
Este exemplo mostra como configurar um <xref:System.Windows.Controls.TextBox> controle por não permitir a entrada do usuário ou modificação.  
  
## <a name="example"></a>Exemplo  
 Para impedir que usuários modifiquem o conteúdo de um <xref:System.Windows.Controls.TextBox> , defina a <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> atributo **verdadeiro**.  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 O <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> atributo afeta somente a entrada do usuário, ela não afeta o texto definido na [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] descrição de uma <xref:System.Windows.Controls.TextBox> controle ou definida programaticamente através de texto o <xref:System.Windows.Controls.TextBox.Text%2A> propriedade.  
  
 O valor padrão de <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> está **falso**.  
  
## <a name="see-also"></a>Consulte também

- [Visão geral de TextBox](textbox-overview.md)
- [Visão geral de RichTextBox](richtextbox-overview.md)
