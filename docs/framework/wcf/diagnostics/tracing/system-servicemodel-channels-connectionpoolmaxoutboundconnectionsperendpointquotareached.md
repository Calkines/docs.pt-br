---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 93c96d94aaeddeb7e7b04ea80645b8de95b0343e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143319"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a>Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
O serviço de protocolo WS-AT não conseguiu se inscrever em uma transação usando o contexto de coordenação fornecido.  
  
## <a name="description"></a>Descrição  
 Rastreada quando o MSDTC não é capaz de se inscrever em uma transação para um protocolo 2pc determinado.  Isso pode acontecer porque a transação não existe mais, a inscrição não é mais permitida ou muitas inscrições já estão presentes.  
  
## <a name="troubleshooting"></a>Solução de problemas  
 Inspecione a cadeia de caracteres de status dentro da mensagem de rastreamento para determinar se há qualquer item acionável.  
  
## <a name="see-also"></a>Consulte também

- [Rastreamento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Usando o rastreamento para solucionar problemas do seu aplicativo](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Administração e diagnósticos](../../../../../docs/framework/wcf/diagnostics/index.md)
