---
title: Recursos do sistema operacional exigidos pelo WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 828d656370efd7638fa4cf367b84ee7b316b89bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100924"
---
# <a name="operating-system-resources-required-by-wcf"></a>Recursos do sistema operacional exigidos pelo WCF
Windows Communication Foundation (WCF) depende de vários recursos que são fornecidos pelo sistema operacional para a função. A tabela a seguir lista esses recursos.  
  
|Recurso|Descrição|  
|--------------|-----------------|  
|Coordenador de Transações Distribuídas da Microsoft (MSDTC)|Necessário para dar suporte a transações OleTx.|  
|Serviços de Informações da Internet (IIS)|Obrigatório se você quiser usar o IIS para hospedar seu aplicativo.|  
|Serviço de Ativação de Processos do Windows (WAS)|Obrigatório se você quiser usar o WAS para hospedar seu aplicativo.|  
  
## <a name="see-also"></a>Consulte também

- [Requisitos do sistema](../../../docs/framework/wcf/wcf-system-requirements.md)
