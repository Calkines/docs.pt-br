---
title: Enumeração CLR_DEBUGGING_PROCESS_FLAGS
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8321e5aeba435ca5f1398a9cb827a93ae821d686
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217322"
---
# <a name="clrdebuggingprocessflags-enumeration"></a>Enumeração CLR_DEBUGGING_PROCESS_FLAGS
Fornece valores que são usados pela [iclrdebugging:: Openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) método.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|Descrição|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|Esse tempo de execução tem um evento do depurador gerenciado de não-catch-up para enviar. Consulte a seção comentários para a distinção entre eventos de atualização e não-catch-up.|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|O evento gerenciado que está pendente é um <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> solicitação.|  
  
## <a name="remarks"></a>Comentários  
 Ajuste de eventos incluem processo, domínio de aplicativo, assembly, módulo e as notificações de criação do thread que trazem o depurador até o estado atual depois que ele foi anexado a um processo. Eventos de não-catch-up, que são indicados pela `CLR_DEBUGGING_MANAGED_EVENT_PENDING` sinalizar, inclua todos os outros eventos do depurador, como exceções e gerenciados de depuração notificações de MDA (Assistente).  
  
 O `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` sinalizador permite que o tempo de execução diferenciar entre uma exceção de terminação e uma solicitação para anexar um depurador gerenciado que pode ser cancelado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** Metahost.idl, Metahost.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte também

- [Declarando enumerações](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Depuração](../../../../docs/framework/unmanaged-api/debugging/index.md)
