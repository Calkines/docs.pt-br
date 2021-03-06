---
title: Método ICorDebugController::HasQueuedCallbacks
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce6ad24e5e670db21d3a6942ab4650a68ae44568
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102682"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>Método ICorDebugController::HasQueuedCallbacks
Obtém um valor que indica se qualquer retorno de chamada gerenciado atualmente na fila para o thread especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `pThread`  
 [in] Um ponteiro para um objeto de "ICorDebugThread" que representa o thread.  
  
 `pbQueued`  
 [out] Um ponteiro para um valor que é `true` se qualquer retorno de chamada gerenciado está atualmente na fila para o segmento especificado; caso contrário, `false`.  
  
 Se null for especificado para o `pThread` parâmetro, `HasQueuedCallbacks` retornará `true` se não houver gerenciados retornos de chamada na fila para qualquer thread.  
  
## <a name="remarks"></a>Comentários  
 Retornos de chamada será expedido um por vez, cada vez [icordebugcontroller:: continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) é chamado. O depurador pode verificar esse sinalizador se deseja relatar vários eventos de depuração que ocorrem ao mesmo tempo.  
  
 Quando eventos de depuração são enfileirados, eles já ocorreram, portanto, o depurador deve drenar a fila inteira para ter certeza do estado do elemento a ser depurado. (Chamar `ICorDebugController::Continue` para diminuir a fila.) Por exemplo, se a fila contém dois eventos de depuração no thread *X*, e o depurador suspende o thread *X* após o primeiro evento de depuração e, em seguida, chama `ICorDebugController::Continue`, o segundo evento de depuração para thread *X* será expedido, embora o thread foi suspenso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também
