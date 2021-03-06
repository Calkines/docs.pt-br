---
title: 'Como: Buscar um relógio de forma síncrona'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
ms.openlocfilehash: 9b6b1f5523effc56ccd9ddaa4f478e1d3a20ada8
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355981"
---
# <a name="how-to-seek-a-clock-synchronously"></a>Como: Buscar um relógio de forma síncrona
Use o <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> método para buscar um relógio para um ponto específico de forma síncrona. O exemplo a seguir demonstra a ambos os <xref:System.Windows.Media.Animation.ClockController.Seek%2A> e <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> métodos de um <xref:System.Windows.Media.Animation.ClockController>.  
  
 Este exemplo mostra como buscar uma <xref:System.Windows.Media.Animation.Clock>; para obter um exemplo que mostra como buscar um storyboard, consulte [buscar um Storyboard forma síncrona](how-to-seek-a-storyboard-synchronously.md) .  
  
## <a name="example"></a>Exemplo  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
