---
title: 'Como: personalizar uma associação fornecida pelo sistema'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8b97862-e8bb-470d-8b96-07733c21fe26
ms.openlocfilehash: 0c5474a65bee7d3d290372e79f8423ea9986235f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59301172"
---
# <a name="how-to-customize-a-system-provided-binding"></a>Como: personalizar uma associação fornecida pelo sistema
Windows Communication Foundation (WCF) inclui várias associações fornecidas pelo sistema que permitem que você configure algumas das propriedades dos elementos de associação subjacente, mas não todas as propriedades. Este tópico demonstra como definir propriedades nos elementos de associação para criar uma associação personalizada.  
  
 Para obter mais informações sobre como criar e configurar os elementos de associação sem usar as associações fornecidas pelo sistema de diretamente, consulte [ligações personalizadas](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
 Para obter mais informações sobre como criar e estender associações personalizadas, consulte [estendendo associações](../../../../docs/framework/wcf/extending/extending-bindings.md).  
  
 No WCF todas as associações são compostas de *elementos de associação*. Cada elemento de associação deriva o <xref:System.ServiceModel.Channels.BindingElement> classe. Associações fornecidas pelo sistema, como <xref:System.ServiceModel.BasicHttpBinding> criar e configurar seus próprios elementos de associação. Este tópico mostra como acessar e alterar as propriedades desses elementos de associação, que não são diretamente expostos na associação; Especificamente, o <xref:System.ServiceModel.BasicHttpBinding> classe.  
  
 Os elementos de associação individuais estão contidos em uma coleção representada pelo <xref:System.ServiceModel.Channels.BindingElementCollection> de classe e são adicionadas nesta ordem: Fluxo de transações, sessão confiável, segurança, dúplex de composição, unidirecional, segurança de Stream, codificação de mensagem e transporte. Observe que nem todos os elementos de associação listados são necessárias em todas as associações. Elementos de associação definidas pelo usuário também podem aparecer nesta coleção de elemento de associação e devem aparecer na mesma ordem conforme descrito anteriormente. Por exemplo, um transporte definido pelo usuário deve ser o último elemento da coleção do elemento de associação.  
  
 O <xref:System.ServiceModel.BasicHttpBinding> classe contém três elementos de ligação:  
  
1. Um elemento de associação seja opcional de segurança de <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> classe usada com o transporte HTTP (segurança em nível de mensagem) ou o <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> classe, que é usado quando a camada de transporte oferece segurança, nesse caso, o transporte HTTPS é usado.  
  
2. Um codificador de mensagem necessário ou elemento de associação <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> ou <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.  
  
3. Um transporte obrigatório ou elemento de associação <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, ou <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.  
  
 Neste exemplo, podemos criar uma instância da associação, gerar uma *ligação personalizada* dele, examine os elementos de associação na associação personalizado, e ao encontrar o elemento de associação de HTTP, definimos seu `KeepAliveEnabled` propriedade `false`. O `KeepAliveEnabled` propriedade não é exposta diretamente no `BasicHttpBinding`, portanto, devemos criar uma ligação personalizada para navegar até o elemento de associação e definir essa propriedade.  
  
### <a name="to-modify-a-system-provided-binding"></a>Para modificar uma associação fornecida pelo sistema  
  
1. Criar uma instância do <xref:System.ServiceModel.BasicHttpBinding> de classe e definir seu modo de segurança para o nível de mensagem.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#1)]
     [!code-vb[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#1)]  
  
2. Criar uma ligação personalizada da associação e criar um <xref:System.ServiceModel.Channels.BindingElementCollection> classe a partir de uma das propriedades da associação personalizada.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#2)]
     [!code-vb[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#2)]  
  
3. Percorra o <xref:System.ServiceModel.Channels.BindingElementCollection> classe, e quando você encontrar o <xref:System.ServiceModel.Channels.HttpTransportBindingElement> classe, defina seu <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> propriedade para `false`.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#3)]
     [!code-vb[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#3)]  
  
## <a name="see-also"></a>Consulte também

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Associações personalizadas](../../../../docs/framework/wcf/extending/custom-bindings.md)
