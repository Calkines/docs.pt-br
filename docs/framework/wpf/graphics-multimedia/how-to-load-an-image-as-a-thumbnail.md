---
title: 'Como: Carregar uma imagem como uma miniatura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
ms.openlocfilehash: f984293a395e925368b20cef6aa0cd902bd6fc15
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134037"
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a>Como: Carregar uma imagem como uma miniatura
Os exemplos a seguir mostram como carregar um <xref:System.Windows.Controls.Image> como uma miniatura para conservar a memória do aplicativo.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir define o <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> propriedade de um <xref:System.Windows.Media.Imaging.BitmapImage> no [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para reduzir a memória necessária para carregar a imagem.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir define o <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> propriedade de um <xref:System.Windows.Media.Imaging.BitmapImage> no código para reduzir a memória necessária para carregar a imagem.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>Consulte também

- [Visão geral da geração de imagens](imaging-overview.md)
