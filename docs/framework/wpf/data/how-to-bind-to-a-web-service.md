---
title: 'Como: Associar a um serviço Web'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
ms.openlocfilehash: 2c3bc1f2142f07aba3df2da6c46117d3907443a5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304981"
---
# <a name="how-to-bind-to-a-web-service"></a>Como: Associar a um serviço Web
Este exemplo mostra como associar a objetos retornados por chamadas de método de serviço Web.  
  
## <a name="example"></a>Exemplo  
 Este exemplo usa o [serviço de conteúdo de sistema de publicação MSDN/TechNet (MTPS)](https://go.microsoft.com/fwlink/?LinkId=95677) para recuperar a lista de idiomas com suporte de um documento especificado.  
  
 Antes de chamar um serviço Web, é necessário criar uma referência a ele. Para criar uma referência Web ao serviço MTPS usando [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], siga as etapas a seguir:  
  
1. Abra o projeto no [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].  
  
2. No menu **Projeto**, clique em **Adicionar referência Web**.  
  
3. Na caixa de diálogo, defina as **URL** à [ http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl ](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).  
  
4. Pressione **Ir** e, em seguida, **Adicionar referência**.  
  
 Em seguida, chame o método de serviço Web e defina o <xref:System.Windows.FrameworkElement.DataContext%2A> do controle ou janela apropriados para o objeto retornado. O método **GetContent** do serviço MTPS utiliza uma referência para o objeto **getContentRequest**. Portanto, o exemplo a seguir primeiro define um objeto de solicitação:  
  
 [!code-csharp[BindToWebService#Namespace](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 Após o <xref:System.Windows.FrameworkElement.DataContext%2A> tiver sido definido, você pode criar associações às propriedades do objeto que o <xref:System.Windows.FrameworkElement.DataContext%2A> foi definido como. Neste exemplo, o <xref:System.Windows.FrameworkElement.DataContext%2A> é definido como o **getContentResponse** objeto retornado pelo **GetContent** método. No exemplo a seguir, o <xref:System.Windows.Controls.ItemsControl> associa e exibe as **localidade** valores de **availableVersionsAndLocales** de **getContentResponse**.  
  
 [!code-xaml[BindToWebService#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 Para obter informações sobre a estrutura de **getContentResponse**, consulte a [Documentação do serviço de conteúdo](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).  
  
## <a name="see-also"></a>Consulte também

- [Visão geral da vinculação de dados](data-binding-overview.md)
- [Visão geral das origens da associação](binding-sources-overview.md)
- [Disponibilizar dados para associação em XAML](how-to-make-data-available-for-binding-in-xaml.md)
