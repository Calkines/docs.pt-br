---
title: 'O modelo de objeto Ink: Windows Forms e COM versus WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling ink [WPF]
- InkCanvas control [WPF]
- ink object model [WPF]
- tablet pen [WPF], events [WPF]
- ink [WPF], enabling
- events [WPF], tablet pen
ms.assetid: 577835be-b145-4226-8570-1d309e9b3901
ms.openlocfilehash: 68003943041fe0ba405eff1236c43a8e7e9c2b71
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356826"
---
# <a name="the-ink-object-model-windows-forms-and-com-versus-wpf"></a>O modelo de objeto Ink: Windows Forms e COM versus WPF

Há basicamente três plataformas que dão suporte à tinta digital: a plataforma Tablet PC Windows Forms, a plataforma Tablet PC COM e a plataforma Windows Presentation Foundation (WPF).  As plataformas Windows Forms e COM compartilham um modelo de objeto semelhante, mas o modelo de objeto para a plataforma [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] é significativamente diferente.  Este tópico discute as diferenças em um alto nível para que os desenvolvedores que trabalharam com um modelo de objetos possam entender o outro.  
  
## <a name="enabling-ink-in-an-application"></a>Habilitando o Ink em um aplicativo  
 Todas as três plataformas vêm com objetos e controles que permitem que um aplicativo receba entrada de uma caneta eletrônica.  O Windows Forms plataformas e COM vêm com [Microsoft.Ink.InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)), [Microsoft.Ink.InkEdit](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90)), [Microsoft.Ink.InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) e [ Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) classes.  [Microsoft.Ink.InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) e [Microsoft.Ink.InkEdit](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90)) são controles que podem ser adicionados a um aplicativo para coletar tinta.  O [Microsoft.Ink.InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) e [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) podem ser anexados a uma janela existente para ativar tinta nas janelas e controles personalizados.  
  
 A plataforma WPF inclui o <xref:System.Windows.Controls.InkCanvas> controle.  Você pode adicionar um <xref:System.Windows.Controls.InkCanvas> ao seu aplicativo e começar a coleta de tinta imediatamente. Com o <xref:System.Windows.Controls.InkCanvas>, o usuário pode copiar, selecionar e redimensionar a tinta.  Você pode adicionar outros controles para o <xref:System.Windows.Controls.InkCanvas>, e o usuário pode fazer manuscritos sobre esses controles, também.  Você pode criar um controle personalizado habilitado para tinta, adicionando um <xref:System.Windows.Controls.InkPresenter> a ele e coletando seus pontos de caneta.  
  
 A tabela a seguir lista em que você pode saber mais sobre como habilitar a tinta em um aplicativo:  
  
|Para fazer isso...|Na plataforma WPF...|Nas plataformas Windows Forms/COM...|  
|-----------------|--------------------------|------------------------------------------|  
|Adicionar um controle habilitado para tinta a um aplicativo|Consulte [Introdução à tinta](getting-started-with-ink.md).|Consulte [Exemplo de formulário de declarações automáticas](/windows/desktop/tablet/auto-claims-form-sample)|  
|Habilitar tinta em um controle personalizado|Consulte [Criando um controle de entrada de tinta](creating-an-ink-input-control.md).|Consulte [Exemplo da área de transferência de tinta](/windows/desktop/tablet/ink-clipboard-sample).|  
  
## <a name="ink-data"></a>Dados de tinta  
 Nas plataformas de COM e Windows Forms [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)), [Microsoft.Ink.InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)), [Microsoft.Ink.InkEdit](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90)), e [ Microsoft.Ink.InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) expõem uma [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) objeto. O [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) objeto contém os dados para um ou mais [Microsoft.Ink.Stroke](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) objetos e expõe métodos e propriedades comuns para gerenciar e manipular esses traços.  O [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) objeto gerencia o tempo de vida dos traços que ele contém; a [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) objeto cria e exclui os traços que ele possui.  Cada [Microsoft.Ink.Stroke](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) tem um identificador que é exclusivo dentro de seu pai [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) objeto.  
  
 Na plataforma do WPF, o <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> classe possui e gerencia seu próprio tempo de vida. Um grupo de <xref:System.Windows.Ink.Stroke> objetos podem ser coletados juntos em um <xref:System.Windows.Ink.StrokeCollection>, que fornece métodos para tinta comuns operações de gerenciamento de dados, como atingir o teste, apagar, transformar e serializar a tinta. Um <xref:System.Windows.Ink.Stroke> pode pertencer a zero, um ou mais <xref:System.Windows.Ink.StrokeCollection> dar a objetos em qualquer tempo.  Em vez de ter uma [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) objeto, o <xref:System.Windows.Controls.InkCanvas> e <xref:System.Windows.Controls.InkPresenter> contêm um <xref:System.Windows.Ink.StrokeCollection?displayProperty=nameWithType>.  
  
 O par de ilustrações a seguir compara os modelos de objeto de dados de tinta.  Nos Windows Forms e COM plataformas, o [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) objeto limita o tempo de vida da [Microsoft.Ink.Stroke](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) objetos e os pacotes da caneta pertencem aos traços individuais.  Dois ou mais traços podem referenciar o mesmo [Microsoft.Ink.DrawingAttributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583636(v=vs.90)) do objeto, conforme mostrado na ilustração a seguir.  
  
 ![Diagrama do modelo de objeto de tinta para COM&#47;Winforms.](./media/ink-inkownsstrokes.png "Ink_InkOwnsStrokes")  
  
 Sobre o [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], cada <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> é um objeto common language runtime que existe enquanto algo tem uma referência a ele.  Cada <xref:System.Windows.Ink.Stroke> referências de um <xref:System.Windows.Input.StylusPointCollection> e <xref:System.Windows.Ink.DrawingAttributes?displayProperty=nameWithType> objeto, que também são objetos common language runtime.  
  
 ![Diagrama do modelo de objeto de tinta para WPF.](./media/ink-wpfinkobjectmodel.png "Ink_WPFInkObjectModel")  
  
 A tabela a seguir compara como realizar algumas tarefas comuns na plataforma [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] e nas plataformas Windows Forms e COM.  
  
|Tarefa|Windows Presentation Foundation|Windows Forms e COM|  
|----------|-------------------------------------|---------------------------|  
|Salvar tinta|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|[Microsoft.Ink.Ink.Save](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571335(v=vs.90))|  
|Carregar tinta|Criar uma <xref:System.Windows.Ink.StrokeCollection> com o <xref:System.Windows.Ink.StrokeCollection.%23ctor%2A> construtor.|[Microsoft.Ink.Ink.Load](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms569609(v=vs.90))|  
|Teste de clique|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|[Microsoft.Ink.Ink.HitTest](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571330(v=vs.90))|  
|Copiar tinta|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|[Microsoft.Ink.Ink.ClipboardCopy](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571316(v=vs.90))|  
|Colar tinta|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|[Microsoft.Ink.Ink.ClipboardPaste](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571318(v=vs.90))|  
|Acessar propriedades personalizadas em uma coleção de traços|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> (as propriedades são armazenadas internamente e acessadas por meio <xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>, <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A>, e <xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>)|Use [Microsoft.Ink.Ink.ExtendedProperties](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms582214(v=vs.90))|  
  
### <a name="sharing-ink-between-platforms"></a>Compartilhando tinta entre plataformas  
 Embora as plataformas tenham modelos de objeto diferentes para os dados de tinta, o compartilhamento de dados entre as plataformas é muito fácil. Os exemplos a seguir salva a tinta de um aplicativo Windows Forms e carregam a tinta em um aplicativo do Windows Presentation Foundation.  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 Os exemplos a seguir salvam a tinta de um aplicativo Windows Presentation Foundation e carregam a tinta em um aplicativo dos Windows Forms.  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]
## <a name="events-from-the-tablet-pen"></a>Eventos da caneta eletrônica  

 O [Microsoft.Ink.InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)), [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)), e [Microsoft.Ink.InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) no Windows Forms e COM plataformas recebem eventos quando o usuário Fornece dados da caneta. O [Microsoft.Ink.InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) ou [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) está anexado a uma janela ou um controle e pode assinar os eventos gerados pelos dados de entrada do tablet. O thread em que esses eventos ocorrem depende de se os eventos são gerados com uma caneta, um mouse ou programaticamente. Para obter mais informações sobre o uso de threads em relação a esses eventos, consulte [Considerações gerais de thread](/windows/desktop/tablet/general-threading-considerations) e [Threads nos quais um evento pode ser acionado](/windows/desktop/tablet/threads-on-which-an-event-can-fire).  
  
 Na plataforma Windows Presentation Foundation, o <xref:System.Windows.UIElement> classe tem eventos para entrada de caneta. Isso significa que cada controle expõe o conjunto completo de eventos de caneta.  Os eventos de caneta têm pares de eventos de túnel/propagação e sempre ocorrem no thread do aplicativo.  Para obter mais informações, consulte [Visão geral de eventos roteados](routed-events-overview.md).  
  
 O diagrama a seguir compara os modelos de objeto para as classes que geram eventos de caneta. O modelo de objeto do Windows Presentation Foundation mostra somente os eventos de propagação, não os equivalentes do evento de túnel.  
  
 ![Diagrama dos eventos da caneta no WPF versus Winforms.](./media/ink-stylusevents.png "Ink_StylusEvents")  
  
## <a name="pen-data"></a>Dados da caneta  
 Todas as três plataformas fornecem meios para interceptar e manipular os dados provenientes de uma caneta eletrônica.  Nas plataformas COM e Windows Forms, isso é feito com a criação de um [Microsoft.StylusInput.RealTimeStylus](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90)), anexando uma janela ou controle a ele e criando uma classe que implementa o [ Microsoft.StylusInput.IStylusSyncPlugin](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms575201(v=vs.90)) ou [Microsoft.StylusInput.IStylusAsyncPlugin](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms575194(v=vs.90)) interface. O plug-in personalizado é adicionado à coleção de plug-in a [Microsoft.StylusInput.RealTimeStylus](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90)). Para obter mais informações sobre esse modelo de objeto, consulte [Arquitetura de APIs StylusInput](/windows/desktop/tablet/architecture-of-the-stylusinput-apis).  
  
 Sobre o [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] plataforma, o <xref:System.Windows.UIElement> classe expõe uma coleção de plug-ins, semelhantes no design para o [Microsoft.StylusInput.RealTimeStylus](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90)).  Para interceptar dados da caneta, crie uma classe que herda de <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> e adicione o objeto para o <xref:System.Windows.UIElement.StylusPlugIns%2A> coleção do <xref:System.Windows.UIElement>. Para obter mais informações sobre essa interação, consulte [Interceptando a entrada da caneta](intercepting-input-from-the-stylus.md).  
  
 Em todas as plataformas, um pool de threads recebe os dados de tinta por eventos de caneta e o envia para o thread do aplicativo.  Para obter mais informações sobre uso de threads nas plataformas Windows e COM, consulte [Considerações de thread para APIs StylusInput](/windows/desktop/tablet/threading-considerations-for-the-stylusinput-apis).  Para obter mais informações sobre uso de threads no software Windows Presentation, consulte [O modelo de threading de tinta](the-ink-threading-model.md).  
  
 A ilustração a seguir compara os modelos de objeto para as classes que recebem dados da caneta no pool de threads de caneta.  
  
 ![Diagrama do WPF do modelo StylusPlugin vs Winforms.](./media/ink-stylusplugins.png "Ink_StylusPlugins")
