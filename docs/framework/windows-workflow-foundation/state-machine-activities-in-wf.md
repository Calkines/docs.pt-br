---
title: Atividades do computador de estado em WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 5aee2a7cb078d9d62c9296f7dda9f28ff812a88a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120907"
---
# <a name="state-machine-activities-in-wf"></a>Atividades do computador de estado em WF
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] fornece vários sistema forneceu atividades e designer de atividade criando fluxos de trabalho do computador de estado.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Executes continha atividades usando o paradigma familiar do computador de estado.|  
|<xref:System.Activities.Statements.State>|Representa um estado em uma máquina de estado.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Representa um estado de terminação em um computador de estado. <xref:System.Activities.Core.Presentation.FinalState> é um designer de atividade que quando usado criar <xref:System.Activities.Statements.State> pré-configurado como um estado de terminação. Para obter mais informações, consulte [Designer de atividade de FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).|  
|<xref:System.Activities.Statements.Transition>|Representa a transição entre dois estados. Não há nenhuma **caixa de ferramentas** item para <xref:System.Activities.Statements.Transition>; as transições são criados no designer de fluxo de trabalho arrastando e soltando uma linha entre dois estados, ou soltando um estado em triângulos que aparecem quando um estado é focalizado sobre outro . Para obter mais informações, consulte [Designer de atividade Transition](/visualstudio/workflow-designer/transition-activity-designer).|  
  
## <a name="see-also"></a>Consulte também

- [Tutorial de Introdução](getting-started-tutorial.md)
