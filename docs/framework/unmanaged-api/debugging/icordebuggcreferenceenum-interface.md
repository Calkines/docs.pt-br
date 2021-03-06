---
title: Interface ICorDebugGCReferenceEnum
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8f83d2ac9ca96145fa89b283fec42c71858097f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080820"
---
# <a name="icordebuggcreferenceenum-interface"></a>Interface ICorDebugGCReferenceEnum
Fornece um enumerador para objetos que serão coletados do lixo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descrição|  
|------------|-----------------|  
|[Método Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|Obtém o número especificado de [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instâncias que contêm informações sobre os objetos que serão coletados pelo lixo.|  
  
## <a name="remarks"></a>Comentários  
 O `ICorDebugGCReferenceEnum` interface implementa a interface "ICorDebugEnum".  
  
 Uma `ICorDebugGCReferenceEnum` instância é preenchida com [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instâncias chamando o [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) método. [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objetos que podem ser enumerados chamando o [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) método.  
  
 O [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objetos na coleção populado por esse método representam três tipos de objetos:  
  
-   Objetos de todas as pilhas gerenciadas. Isso inclui referências ao vivo em código gerenciado, bem como os objetos criados pelo common language runtime.  
  
-   Objetos da tabela de identificador. Isso inclui referências fortes (`HNDTYPE_STRONG` e `HNDTYPE_REFCOUNT`) e as variáveis estáticas em um módulo.  
  
-   Objetos de fila do finalizador. A fila de finalizadores raízes objetos até que o finalizador foi executado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte também

- [Depurando interfaces](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
