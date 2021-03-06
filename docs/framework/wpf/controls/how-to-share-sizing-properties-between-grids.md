---
title: 'Como: Compartilhar propriedades de dimensionamento entre grades'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: d5ab2ac612d55c8cbc34ae6d7d9d63b9f8aa23e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190334"
---
# <a name="how-to-share-sizing-properties-between-grids"></a>Como: Compartilhar propriedades de dimensionamento entre grades
Este exemplo mostra como compartilhar os dados de dimensionamento de colunas e linhas entre <xref:System.Windows.Controls.Grid> elementos para manter um dimensionamento consistente.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir apresenta duas <xref:System.Windows.Controls.Grid> elementos como elementos filho de um pai <xref:System.Windows.Controls.DockPanel>. O <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> anexados a propriedade de <xref:System.Windows.Controls.Grid> é definido no pai <xref:System.Windows.Controls.DockPanel>.  
  
 O exemplo manipula o valor da propriedade usando dois <xref:System.Windows.Controls.Button> elementos; cada elemento representa um dos valores de propriedade booliana. Quando o <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> o valor da propriedade é definido como `true`, cada membro de coluna ou linha de uma <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> compartilha informações de dimensionamento, independentemente do conteúdo de uma linha ou coluna.  
  
 [!code-xaml[gridIssharedsizescopeProp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 O exemplo de code-behind a seguir trata os métodos que o botão <xref:System.Windows.Controls.Primitives.ButtonBase.Click> aciona eventos. O exemplo grava os resultados dessas chamadas de método <xref:System.Windows.Controls.TextBlock> métodos para os novos valores de propriedade como cadeias de caracteres de saída de get de elementos relacionados ao uso.  
  
 [!code-csharp[gridIssharedsizescopeProp#3](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [Visão geral de painéis](panels-overview.md)
