---
title: Interface ICorDebugClass
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e1ad830e728fbe764085a5808a48e4cacedc595
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133621"
---
# <a name="icordebugclass-interface"></a>Interface ICorDebugClass

Representa um tipo, que pode ser básico ou complexo (isto é, definido pelo usuário). Se o tipo for genérico, `ICorDebugClass` representará o tipo genérico sem instância.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descrição|  
|------------|-----------------|  
|[Método GetModule](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|Obtém o módulo que define essa classe.|  
|[Método GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|Obtém o valor do campo estático especificado.|  
|[Método GetToken](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|Obtém o `TypeDef` token de metadados para essa classe.|  
  
## <a name="remarks"></a>Comentários  
 O `ICorDebugClass` interface representa um tipo genérico não instanciado. A interface ICorDebugType representa um tipo genérico instanciado. Por exemplo, `Hashtable<K, V>` seria representada por `ICorDebugClass`, enquanto `Hashtable<Int32, String>` seria representada pelo `ICorDebugType`.  
  
 Tipos não genéricos são representados por ambos `ICorDebugClass` e `ICorDebugType`. A segunda interface foi introduzida no .NET Framework versão 2.0 para lidar com uma instância de tipo.  
  
> [!NOTE]
>  Essa interface não dá suporte a ser chamada remotamente, entre computadores ou entre processos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também

- [Depurando interfaces](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
