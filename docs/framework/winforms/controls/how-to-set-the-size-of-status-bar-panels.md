---
title: 'Como: Definir o tamanho de painéis da barra de status'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- StatusBar control [Windows Forms], panel size
- status bars [Windows Forms], setting panel size
- panels [Windows Forms], setting size in status bars
ms.assetid: a01bee43-d9eb-4954-84e6-45a93532d08d
ms.openlocfilehash: efd3074aaf018e7226c484061cbacb2eac0be820
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311897"
---
# <a name="how-to-set-the-size-of-status-bar-panels"></a>Como: Definir o tamanho de painéis da barra de status
> [!NOTE]
>  O controle <xref:System.Windows.Forms.ToolStripStatusLabel> substitui e adiciona funcionalidade ao controle <xref:System.Windows.Forms.StatusBar>, no entanto, o controle <xref:System.Windows.Forms.StatusBar> é mantido para compatibilidade com versões anteriores e para uso futuro, se desejado.  
  
 Cada instância das <xref:System.Windows.Forms.StatusBarPanel> classe dentro de uma [controle StatusBar](statusbar-control-windows-forms.md) controle tem um número de propriedades dinâmicas que determinam sua largura e redimensionam o comportamento em tempo de execução.  
  
### <a name="to-set-the-size-of-a-panel"></a>Para definir o tamanho de um painel  
  
1. Em um procedimento, defina a <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>, <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A>, e <xref:System.Windows.Forms.StatusBarPanel.Width%2A> propriedades (ou qualquer subconjunto nele) para a barra de status painéis usando seu índice passado a <xref:System.Windows.Forms.StatusBar.Panels%2A> propriedade do <xref:System.Windows.Forms.StatusBarPanel> coleção.  
  
    ```vb  
    Public Sub SetStatusBarPanelSize()  
    ' Create panel and set text property.  
       StatusBar1.Panels.Add("One")  
    ' Set properties of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(0).Width = 200  
    ' Enable the StatusBar control to display panels.  
       StatusBar1.ShowPanels = True  
        End Sub  
    ```  
  
    ```csharp  
    public void SetStatusBarPanelSize()  
    {  
       // Create panel and set text property.  
       statusBar1.Panels.Add("One");  
       // Set properties of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[0].Width = 200;  
       statusBar1.ShowPanels = true;  
    }  
    ```  
  
    ```cpp  
    public:  
       void SetStatusBarPanelSize()  
       {  
          // Create panel and set text property.  
          statusBar1->Panels->Add("One");  
          // Set properties of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[0]->Width = 200;  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Passo a passo: Atualizando informações da barra de Status em tempo de execução](walkthrough-updating-status-bar-information-at-run-time.md)
- [Como: Determinar qual painel no controle StatusBar dos Windows Forms foi clicado](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [Visão geral do controle StatusBar](statusbar-control-overview-windows-forms.md)
