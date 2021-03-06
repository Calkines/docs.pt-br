---
title: 'Como: Controlar o preenchimento de uma forma composta'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], composite [WPF], controlling fill
- composite shapes [WPF], controlling fill
- graphics [WPF], composite shapes
- fill [WPF], controlling
ms.assetid: c1c94575-9eca-48a5-a49a-2ec65259f229
ms.openlocfilehash: 0ba07d8979a2910ce4ec775493e38c714240f642
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59427468"
---
# <a name="how-to-control-the-fill-of-a-composite-shape"></a>Como: Controlar o preenchimento de uma forma composta
O <xref:System.Windows.Media.GeometryGroup.FillRule%2A> propriedade de um <xref:System.Windows.Media.GeometryGroup> ou um <xref:System.Windows.Media.PathGeometry>, especifica uma "regra" que a forma composta usa para determinar se um determinado ponto é parte da geometria. Há dois valores possíveis para <xref:System.Windows.Media.FillRule>: <xref:System.Windows.Media.FillRule.EvenOdd> e <xref:System.Windows.Media.FillRule.Nonzero>. As seções a seguir descreverão como usar essas duas regras.  
  
 **EvenOdd:** Esta regra determina se um ponto está na região de preenchimento desenhando um raio desse ponto até o infinito em qualquer direção e contando o número de segmentos de caminho dentro da forma especificada que o raio cruza. Se esse número for ímpar, o ponto estará dentro, se for par, o ponto estará fora.  
  
 Por exemplo, o XAML abaixo cria uma forma composta composta por uma série de anéis concêntricos (destino) com um <xref:System.Windows.Media.GeometryGroup.FillRule%2A> definido como <xref:System.Windows.Media.FillRule.EvenOdd>.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleEvenOddValue](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillruleevenoddvalue)]  
  
 A ilustração a seguir mostra a forma criada no exemplo anterior.  
  
 ![Um círculo composto por um anéis concêntricos de série com cores alternadas.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-property.png)  
  
 Na ilustração anterior, observe que o centro e o terceiro anel não estão preenchidos. Isso ocorre porque um raio desenhado de qualquer ponto dentro de qualquer um desses dois anéis passa por um número par de segmentos. Consulte a ilustração a seguir:  
  
 ![Diagrama mostrando os raios EvenOdd desenhados no círculo.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-rays.png)  
  
 **NonZero:** Esta regra determina se um ponto está na região de preenchimento do caminho desenhando um raio desse ponto até o infinito em qualquer direção e, em seguida, examinando os locais em que um segmento da forma cruza o raio. Começando com uma contagem de zero, adicione um sempre que um segmento cruzar o raio da esquerda para a direita e subtraia um sempre que um segmento de caminho cruzar o raio da direita para a esquerda. Após a contagem de cruzamentos, se o resultado for zero, o ponto estará fora do caminho. Caso contrário, ele estará dentro.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValueEllipseGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovalueellipsegeometry)]  
  
 Usando o exemplo anterior, um valor de <xref:System.Windows.Media.FillRule.Nonzero> para <xref:System.Windows.Media.GeometryGroup.FillRule%2A> fornece a ilustração a seguir como resultado:  
  
 ![Um círculo composto por uma série anéis concêntricos todos preenchidos com a mesma cor.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-nonzero.png)  
  
 Como podemos ver, todos os anéis estão preenchidos. Isso acontece porque todos os segmentos estão indo na mesma direção, assim, um raio desenhado de qualquer ponto cruzará um ou mais segmentos e a soma dos cruzamentos não será igual a zero. Por exemplo, na ilustração a seguir, as setas vermelhas representam a direção em que os segmentos são desenhados e a seta branca representa um raio arbitrário que de um ponto em que o anel mais interno. Iniciando com um valor de zero, para cada segmento que o raio cruza, um valor de um é adicionado, já que o segmento cruza o raio da esquerda para a direita.  
  
 ![Diagrama mostrando o valor da propriedade FillRule igual a Nonzero.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-equal-nonzero.png)  
  
 Para demonstrar melhor o comportamento de <xref:System.Windows.Media.FillRule.Nonzero> regra uma forma mais complexa com segmentos indo em direções diferentes é necessária. O código XAML abaixo cria uma forma semelhante ao exemplo anterior, exceto que ela é criada com um <xref:System.Windows.Media.PathGeometry> , em seguida, em vez disso, um <xref:System.Windows.Media.EllipseGeometry> que cria quatro arcos concêntricos, em vez círculos concêntricos totalmente fechados.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValuePathGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovaluepathgeometry)]  
  
 A ilustração a seguir mostra a forma criada no exemplo anterior.  
  
 ![Um círculo composto por um anéis concêntricos de série com cores alternadas com o terceiro arco não preenchido.](./media/how-to-control-the-fill-of-a-composite-shape/pathgeometry-concentric-arcs.png)  
  
 Observe que o terceiro arco partindo do centro não está preenchido. A ilustração a seguir mostra por que isso é. Na ilustração, as setas vermelhas representam a direção em que os segmentos são desenhados. As duas setas brancas representam dois raios arbitrários que se movem para fora de um ponto na região "não preenchida". Como podemos ver na ilustração, a soma dos valores de um determinado raio que cruza os segmentos no seu caminho é zero. Conforme definido acima, uma soma zero significa que o ponto não faz parte da geometria (não faz parte do preenchimento), enquanto uma soma que *não* é zero, incluindo um valor negativo, faz parte da geometria.  
  
 ![Diagrama mostrando os segmentos de cruzamento de raios arbitrários.](./media/how-to-control-the-fill-of-a-composite-shape/arbitrary-ray-cross-segment.png)  
  
 **Observação:** Para fins de <xref:System.Windows.Media.FillRule>, todas as formas são consideradas fechadas. Se houver uma lacuna em um segmento, desenhe uma linha imaginária para fechá-la. No exemplo acima, existem pequenas lacunas nos anéis. Devido a isso, seria possível erar que um raio que passasse pela lacuna gerasse um resultado diferente que um raio indo para outra direção. Abaixo está uma ilustração ampliada de uma dessas lacunas e do "segmento imaginário" (segmento desenhado para fins de aplicar o <xref:System.Windows.Media.FillRule>) que o fecha.  
  
 ![Diagrama mostrando FillRule segmentos que estão sempre fechados.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-closed-segments.png)  
  
## <a name="example"></a>Exemplo  
  
## <a name="see-also"></a>Consulte também

- [Criar uma forma composta](how-to-create-a-composite-shape.md)
- [Visão geral de geometria](geometry-overview.md)
