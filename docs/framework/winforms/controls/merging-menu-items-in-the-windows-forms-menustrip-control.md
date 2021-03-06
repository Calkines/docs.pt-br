---
title: Mesclando itens de menu no controle MenuStrip dos Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- merging [Windows Forms], general concepts
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
ms.openlocfilehash: dbe1c0325499e7b925d504fc80f9034f9e387475
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59231559"
---
# <a name="merging-menu-items-in-the-windows-forms-menustrip-control"></a>Mesclando itens de menu no controle MenuStrip dos Windows Forms
Se tiver um aplicativo de interface MDI, você poderá mesclar os itens de menu ou os menus inteiros do formulário filho com os menus do formulário pai.  
  
 Este tópico descreve os conceitos básicos associados aos itens de menu de mesclagem em um aplicativo MDI.  
  
## <a name="general-concepts"></a>Conceitos gerais  
 Os procedimentos de mesclagem envolvem um controle do código-fonte e de destino:  
  
-   O destino é o <xref:System.Windows.Forms.MenuStrip> controle sobre o formulário pai MDI ou principal no qual você está mesclando itens de menu.  
  
-   A fonte é o <xref:System.Windows.Forms.MenuStrip> controle no formulário filho MDI que contém os itens de menu que você deseja mesclar com o menu de destino.  
  
 O <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> propriedade identifica o item de menu filho MDI do formulário de pai cuja lista suspensa você preencherá com títulos da MDI atual. Por exemplo, você normalmente lista o filho MDI que está aberto no momento no menu **Janela**.  
  
 O <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> propriedade identifica quais itens de menu provêm de um <xref:System.Windows.Forms.MenuStrip> em um formulário MDI filho.  
  
 Você pode mesclar itens de menu de forma manual ou automática. Os itens de menu são mesclados da mesma maneira para os dois métodos, mas a mesclagem é ativada de forma diferente, conforme discutido nas seções "Mesclagem manual" e "Mesclagem automática" neste tópico. Tanto na mesclagem manual quanto na automática, cada ação de mesclagem afeta a próxima.  
  
 <xref:System.Windows.Forms.MenuStrip> Mesclando move os itens de menu de um <xref:System.Windows.Forms.ToolStrip> para outro, em vez de cloná-los, como era o caso com <xref:System.Windows.Forms.MainMenu>.  
  
## <a name="mergeaction-values"></a>Valores de MergeAction  
 Defina a ação de mesclagem nos itens de menu na fonte <xref:System.Windows.Forms.MenuStrip> usando o <xref:System.Windows.Forms.MergeAction> propriedade.  
  
 A tabela a seguir descreve o significado e o uso típico das ações de mesclagem disponíveis.  
  
|Valor de MergeAction|Descrição|Uso típico|  
|-----------------------|-----------------|-----------------|  
|<xref:System.Windows.Forms.MergeAction.Append>|(Padrão) Adiciona o item de origem ao final da coleção do item de destino.|Adicionar itens de menu no final do menu quando alguma parte do programa é ativada.|  
|<xref:System.Windows.Forms.MergeAction.Insert>|Adiciona o item de origem à coleção do item de destino, no local especificado pelo <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> propriedade definida no item de origem.|Adicionar itens de menu no início ou no meio do menu quando alguma parte do programa é ativada.<br /><br /> Se o valor de <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> é o mesmo para ambos os itens de menu, eles são adicionados na ordem inversa. Definir <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> adequadamente para preservar a ordem original.|  
|<xref:System.Windows.Forms.MergeAction.Replace>|Localizará uma correspondência de texto ou usará o <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valor se nenhuma correspondência de texto for encontrada e, em seguida, substitui o item de menu de destino correspondente pelo item de menu de origem.|Substituir um item de menu de destino por um item de menu de origem de mesmo nome que faz algo diferente.|  
|<xref:System.Windows.Forms.MergeAction.MatchOnly>|Localizará uma correspondência de texto ou usará o <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valor se nenhuma correspondência de texto for encontrada e, em seguida, adiciona todos os itens de menu suspenso da origem ao destino.|Criar uma estrutura de menu que insere ou adiciona itens de menu em um submenu ou remove itens de menu de um submenu. Por exemplo, você pode adicionar um item de menu de um filho MDI para um principal <xref:System.Windows.Forms.MenuStrip> **Salvar como** menu.<br /><br /> <xref:System.Windows.Forms.MergeAction.MatchOnly> permite que você navegue pela estrutura do menu sem realizar nenhuma ação. Ele fornece uma maneira de avaliar os itens subsequentes.|  
|<xref:System.Windows.Forms.MergeAction.Remove>|Localizará uma correspondência de texto ou usará o <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> valor se nenhuma correspondência de texto for encontrada e, em seguida, remove o item de destino.|Remover um item de menu do destino <xref:System.Windows.Forms.MenuStrip>.|  
  
## <a name="manual-merging"></a>Manual de mesclagem  
 Somente <xref:System.Windows.Forms.MenuStrip> controles participam da mesclagem automática. Para combinar os itens de outros controles, como <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.StatusStrip> controles, você deve mesclá-los manualmente, chamando o <xref:System.Windows.Forms.ToolStripManager.Merge%2A> e <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> métodos em seu código conforme necessário.  
  
## <a name="automatic-merging"></a>Mesclagem automática  
 Você pode usar a mesclagem automática para aplicativos MDI, ativando o formulário de origem. Para usar um <xref:System.Windows.Forms.MenuStrip> em um aplicativo MDI, defina a <xref:System.Windows.Forms.Form.MainMenuStrip%2A> propriedade para o destino <xref:System.Windows.Forms.MenuStrip> para que a mesclagem de ações executadas na fonte <xref:System.Windows.Forms.MenuStrip> são refletidas no destino <xref:System.Windows.Forms.MenuStrip>.  
  
 Você pode disparar a mesclagem automática, ativando o <xref:System.Windows.Forms.MenuStrip> no MDI de origem. Após a ativação, o código-fonte <xref:System.Windows.Forms.MenuStrip> é mesclada no MDI de destino. Quando um novo formulário se torna ativo, a mesclagem é revertida no último formulário e acionada no novo formulário. Você pode controlar esse comportamento, definindo a <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> propriedade conforme necessário em cada <xref:System.Windows.Forms.ToolStripItem>e definindo o <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> propriedade em cada <xref:System.Windows.Forms.MenuStrip>.  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- [Controle MenuStrip](menustrip-control-windows-forms.md)
- [Como: Criar uma lista de janelas MDI com MenuStrip](how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)
- [Como: Configurar a mesclagem de Menu automática para aplicativos MDI](how-to-set-up-automatic-menu-merging-for-mdi-applications.md)
