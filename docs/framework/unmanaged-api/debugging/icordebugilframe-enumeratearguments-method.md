---
title: Método ICorDebugILFrame::EnumerateArguments
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49d7fb1de0b2ea63c1a766023b23acc42e027af8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475652"
---
# <a name="icordebugilframeenumeratearguments-method"></a>Método ICorDebugILFrame::EnumerateArguments
Obtém um enumerador para os argumentos neste quadro.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `ppValueEnum`  
 [out] Um ponteiro para o endereço de um objeto ICorDebugValueEnum que é o enumerador para os argumentos neste quadro.  
  
## <a name="remarks"></a>Comentários  
 `EnumerateArguments` Obtém um enumerador que pode listar os argumentos disponíveis no quadro de chamada que é representado por esse objeto ICorDebugILFrame. A lista incluirá os argumentos que são [vararg](/cpp/windows/vararg) (ou seja, um número variável de argumentos), bem como os argumentos que não são `vararg`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
