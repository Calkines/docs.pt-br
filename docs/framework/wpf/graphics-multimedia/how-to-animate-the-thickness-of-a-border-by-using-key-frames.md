---
title: 'Como: Animar a espessura de uma borda usando quadros principais'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 101fd077bf125faadbd9a0186c2282e4b20ee78f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59301783"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a>Como: Animar a espessura de uma borda usando quadros principais
Este exemplo mostra como animar a <xref:System.Windows.Controls.Control.BorderThickness%2A> propriedade de um <xref:System.Windows.Controls.Border>.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir usa o <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> classe para animar a <xref:System.Windows.Controls.Control.BorderThickness%2A> propriedade de um <xref:System.Windows.Controls.Border>. Essa animação usa três quadros-chave da seguinte maneira:  
  
1. Durante o primeiro meio segundo, usa uma instância da <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> classe para aumentar gradualmente a espessura da borda. O exemplo usa <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> para criar um aumento linear suave entre valores.  
  
2. No final do próximo meio segundo, usa uma instância da <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> classe para aumentar repentinamente a espessura da borda. Quadros chave discretos como aqueles derivam <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> criam saltos repentinos entre valores, ou seja, o movimento da animação é brusco.  
  
3. Durante os dois segundos finais, usa uma instância da <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> classe para diminuir a espessura da borda. Quadros-chave spline, como aqueles derivam <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> criam uma transição variável entre valores de acordo com os valores da <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> propriedade. Neste quadro-chave, a animação começa lentamente e acelera exponencialmente na direção do final do segmento de tempo.  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 Para ver o exemplo completo, consulte [Exemplo de animação de quadro-chave](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [Visão geral das animações de quadro-chave](key-frame-animations-overview.md)
- [Tópicos explicativos sobre quadros-chave](key-frame-animation-how-to-topics.md)
- [Animar um valor de BorderThickness](../controls/how-to-animate-a-borderthickness-value.md)
