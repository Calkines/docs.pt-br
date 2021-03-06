---
title: 'Como: Localizar o elemento de origem em um manipulador de eventos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
ms.openlocfilehash: 9a49878c9ad8313903df4506796998fd43e2e749
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104553"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a>Como: Localizar o elemento de origem em um manipulador de eventos
Este exemplo mostra como localizar o elemento de origem em um manipulador de eventos.  
  
## <a name="example"></a>Exemplo  
 A exemplo a seguir mostra um <xref:System.Windows.Controls.Primitives.ButtonBase.Click> manipulador de eventos que é declarada em um arquivo code-behind. Quando um usuário clica no botão que o manipulador está anexado a, o manipulador altera um valor da propriedade. O código do manipulador usa a <xref:System.Windows.RoutedEventArgs.Source%2A> propriedade dos dados do evento roteado que são relatados nos argumentos de evento para alterar o <xref:System.Windows.FrameworkElement.Width%2A> valor da propriedade a <xref:System.Windows.RoutedEventArgs.Source%2A> elemento.  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.RoutedEventArgs>
- [Visão geral de eventos roteados](routed-events-overview.md)
- [Tópicos de instruções](events-how-to-topics.md)
