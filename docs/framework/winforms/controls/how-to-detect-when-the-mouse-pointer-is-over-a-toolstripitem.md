---
title: 'Como: Detectar quando o ponteiro do mouse passa sobre um ToolStripItem'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 09fd9f2f9b8cc44b6c04b829bf2854bea4aa8cf7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220039"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a>Como: Detectar quando o ponteiro do mouse passa sobre um ToolStripItem
Use o procedimento a seguir para detectar quando o ponteiro do mouse sobre um <xref:System.Windows.Forms.ToolStripItem>.  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a>Para detectar quando o ponteiro está sobre um ToolStripItem  
  
-   Use o <xref:System.Windows.Forms.ToolStripItem.Selected%2A> propriedade para itens em que <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> é `true`.  
  
     Isso impedirá que você precise sincronizar o <xref:System.Windows.Forms.ToolStripItem.MouseEnter> e <xref:System.Windows.Forms.ToolStripItem.MouseLeave> eventos.  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [Visão geral do controle ToolStrip](toolstrip-control-overview-windows-forms.md)
