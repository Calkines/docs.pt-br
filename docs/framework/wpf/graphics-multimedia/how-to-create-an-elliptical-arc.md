---
title: 'Como: Criar um arco elíptico'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: aae304b9963f3a8e5833b4d8ba0a54777a750225
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183645"
---
# <a name="how-to-create-an-elliptical-arc"></a>Como: Criar um arco elíptico
Este exemplo mostra como desenhar um arco elíptico. Para criar um arco elíptico, use o <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, e <xref:System.Windows.Media.ArcSegment> classes.  
  
## <a name="example"></a>Exemplo  
 Nos exemplos a seguir, um arco elíptico é desenhado de (10,100) a (200,100). O arco tem um <xref:System.Windows.Media.ArcSegment.Size%2A> de 100 por 50 pixels de independentes de dispositivo, uma <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> de 45 graus, um <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> configuração de `true`e um <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> de <xref:System.Windows.Media.SweepDirection.Counterclockwise>.  
  
 [xaml]  
  
 No [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], você pode usar a sintaxe de atributo para descrever um caminho.  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 [xaml]  
  
 (Observe que essa sintaxe de atributo na verdade cria um <xref:System.Windows.Media.StreamGeometry>, uma versão leve de um <xref:System.Windows.Media.PathGeometry>. Para obter mais informações, consulte o [sintaxe de marcação de caminho](path-markup-syntax.md) página.)  
  
 No [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], você também pode desenhar um arco elíptico explicitamente usando marcas de objeto. A seguir é equivalente ao anterior [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcação.  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 Este exemplo é parte de um exemplo maior. Para o exemplo completo, consulte o [exemplo de geometrias](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Consulte também

- [Criar uma curva de Bézier quadrática](how-to-create-a-quadratic-bezier-curve.md)
- [Criar uma curva de Bézier cúbica](how-to-create-a-cubic-bezier-curve.md)
