---
title: 'Como: Adicionar e remover itens com o controle ListView do Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: 8a97d73b9b2c46d02ae0794ad66b20a04db58af6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59327653"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a>Como: Adicionar e remover itens com o controle ListView do Windows Forms
O processo de adicionar um item em um Windows Forms <xref:System.Windows.Forms.ListView> controle consiste principalmente de especificar o item e atribuir propriedades a ele. A adição ou remoção de itens de lista pode ser feita a qualquer momento.  
  
### <a name="to-add-items-programmatically"></a>Para adicionar itens programaticamente  
  
1. Use o <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> método da <xref:System.Windows.Forms.ListView.Items%2A> propriedade.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a>Para remover itens de forma programática  
  
1. Use o <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> ou <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> método o <xref:System.Windows.Forms.ListView.Items%2A> propriedade. O <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> método Remove um item único; o <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> método Remove todos os itens da lista.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.Forms.ListView>
- [Controle ListView](listview-control-windows-forms.md)
- [Visão geral do controle ListView](listview-control-overview-windows-forms.md)
