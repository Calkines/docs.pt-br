---
title: Árvore de elementos e serialização
ms.date: 03/30/2017
f1_keywords:
- AutoGeneratedOrientationPage
helpviewer_keywords:
- element tree [WPF]
- serialization [WPF]
- tree [WPF]
ms.assetid: 8f57e879-180b-421f-b3d0-ac007ff2ce80
ms.openlocfilehash: 4c178213e08add247311f0b71517ed292bd6658a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355799"
---
# <a name="element-tree-and-serialization"></a>Árvore de elementos e serialização
Elementos de programação do WPF geralmente existe em alguma forma de relação de árvore entre si. Por exemplo, um aplicativo de que interface do usuário criada em XAML pode ser conceitualizado como uma árvore de objetos. A árvore de elementos pode ser dividida em duas árvores discretos ainda, às vezes, paralelas: a árvore lógica e a árvore visual. Serialização no WPF envolve salvar o estado dessas duas árvores, bem como o estado do aplicativo e gravá-los em um arquivo, potencialmente, como XAML.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Árvores no WPF](trees-in-wpf.md)  
 [Limitações de serialização de XamlWriter.Save](serialization-limitations-of-xamlwriter-save.md)  
 [Inicialização de elementos de objeto que não estão em uma árvore de objetos](initialization-for-object-elements-not-in-an-object-tree.md)  
 [Tópicos de instruções](element-tree-and-serialization-how-to-topics.md)  
  
## <a name="reference"></a>Referência  
 <xref:System.Windows.Markup>  
  
 <xref:System.Windows.LogicalTreeHelper>  
  
 <xref:System.Windows.Media.VisualTreeHelper>  
  
## <a name="related-sections"></a>Seções relacionadas  
 [Arquitetura do WPF](wpf-architecture.md)  
  [XAML no WPF](xaml-in-wpf.md)  
  [Elementos base](base-elements.md)  
  [Propriedades](properties-wpf.md)  
  [Eventos](events-wpf.md)  
  [Entrada](input-wpf.md)  
  [Recursos](resources-wpf.md)  
  [Estilo e modelagem](../controls/styling-and-templating.md)  
  [Modelo de threading](threading-model.md)
