---
title: Obter propriedades de elemento da automação de interface do usuário
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: 93e0fba4288ba3231bfed45252bdaa78892d008c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330760"
---
# <a name="get-ui-automation-element-properties"></a>Obter propriedades de elemento da automação de interface do usuário
> [!NOTE]
>  Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>. Para obter as informações mais recentes sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automação de interface do usuário](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Este tópico mostra como recuperar propriedades de um [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elemento.  
  
### <a name="get-a-current-property-value"></a>Obter um valor da propriedade atual  
  
1. Obter o <xref:System.Windows.Automation.AutomationElement> cuja propriedade você deseja obter.  
  
2. Chame <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, ou recuperar o <xref:System.Windows.Automation.AutomationElement.Current%2A> estrutura de propriedade e obter o valor de um dos seus membros.  
  
### <a name="get-a-cached-property-value"></a>Obter um valor de propriedade em cache  
  
1. Obter o <xref:System.Windows.Automation.AutomationElement> cuja propriedade você deseja obter. A propriedade deve ter sido especificada no <xref:System.Windows.Automation.CacheRequest>.  
  
2. Chame <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, ou recuperar o <xref:System.Windows.Automation.AutomationElement.Cached%2A> estrutura de propriedade e obter o valor de um dos seus membros.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir mostra várias maneiras de recuperar as propriedades atuais de um <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a>Consulte também

- [Propriedades de automação de interface do usuário para clientes](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)
- [Usar o cache em automação de interface do usuário](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
- [Armazenamento em cache em clientes de automação de interface do usuário](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
