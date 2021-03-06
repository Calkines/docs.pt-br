---
title: 'Como: Agrupar controles RadioButton do Windows Forms para funcionarem como um conjunto'
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: 857e61bc89e072aebcf34793d7e8504ece3318c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307244"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>Como: Agrupar controles RadioButton do Windows Forms para funcionarem como um conjunto
Windows Forms <xref:System.Windows.Forms.RadioButton> controles são projetados para dar aos usuários uma opção entre dois ou mais configurações, dos quais apenas um pode ser atribuído a um procedimento ou objeto. Por exemplo, um grupo de <xref:System.Windows.Forms.RadioButton> controles podem exibir das operadoras de pacote para um pedido, mas apenas uma das operadoras será usada. Portanto, apenas um <xref:System.Windows.Forms.RadioButton> por vez pode ser selecionado, mesmo que ele faz parte de um grupo funcional.  
  
 Grupo de botões de opção ao desenhar dentro de um contêiner, como um <xref:System.Windows.Forms.Panel> controle, um <xref:System.Windows.Forms.GroupBox> controle ou formulário. Todos os botões de opção que forem adicionados diretamente a um formulário se tornam um grupo. Para adicionar grupos separados, você deve inseri-los em painéis ou caixas de grupo. Para obter mais informações sobre painéis ou caixas de grupo, consulte [Visão geral do controle Panel](panel-control-overview-windows-forms.md) ou [Visão geral do controle GroupBox](groupbox-control-overview-windows-forms.md).  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>Para agrupar controles RadioButton como um conjunto para funcionar independentemente dos outros conjuntos  
  
1. Arraste uma <xref:System.Windows.Forms.GroupBox> ou <xref:System.Windows.Forms.Panel> controlar da **Windows Forms** guia o **caixa de ferramentas** para o formulário.  
  
2. Desenhar <xref:System.Windows.Forms.RadioButton> controles em de <xref:System.Windows.Forms.GroupBox> ou <xref:System.Windows.Forms.Panel> controle.  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.Forms.RadioButton>
- [Visão geral do controle RadioButton](radiobutton-control-overview-windows-forms.md)
- [Visão geral do controle Panel](panel-control-overview-windows-forms.md)
- [Visão geral do controle GroupBox](groupbox-control-overview-windows-forms.md)
- [Visão geral do controle CheckBox](checkbox-control-overview-windows-forms.md)
- [Controle RadioButton](radiobutton-control-windows-forms.md)
