---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: 3dd28276cd3a39497c0387f5b9d0adec23d07c37
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182189"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a>System.ServiceModel.Channels.ConnectionPoolCloseException
Ocorreu uma exceção ao fechar as conexões nesse pool de conexão.  
  
## <a name="description"></a>Descrição  
 Rastreamento de nível de erro indica que ocorreu um erro ao fechar os pools de conexão usados pela conexão Windows Communication Foundation (WCF) do pool de recursos. Um motivo possível para isso é um fechamento malsucedido de uma conexão em pool ou um conjunto de conexões em pool dentro de CloseTimeout. Quando essa exceção é lançada, quaisquer conexões não fechadas restantes no pool são anuladas; conexões não fechadas dentro de outros pools são abandonadas.  
  
## <a name="see-also"></a>Consulte também

- [Rastreamento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Usando o rastreamento para solucionar problemas do seu aplicativo](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Administração e diagnósticos](../../../../../docs/framework/wcf/diagnostics/index.md)
