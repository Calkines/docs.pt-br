---
title: Função ClrCreateManagedInstance
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f82303a3d38e7a5baaf1c3edcc41518228360d34
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088451"
---
# <a name="clrcreatemanagedinstance-function"></a>Função ClrCreateManagedInstance
Cria uma instância do tipo gerenciado especificado.  
  
 Essa função foi preterida no [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Usar ativação COM para criar uma instância do tipo gerenciado, ou usar a hospedagem (consulte [CLR hospedando Interfaces adicionadas no .NET Framework 4 e 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `pTypeName`  
 [in] Um ponteiro para o nome do tipo de instância que está sendo solicitado.  
  
 `riid`  
 [in] O `IID` do tipo de instância que está sendo solicitado.  
  
 `ppObject`  
 [out] Um ponteiro para um ponteiro para uma instância do tipo gerenciado que foi solicitada pelo chamador.  
  
## <a name="remarks"></a>Comentários  
 O common language runtime já deve ser carregado em um processo. Por exemplo, pode ser carregado por meio de uma chamada para o [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) funcionar antes do `ClrCreateManagedInstance` função é chamada. Se o tempo de execução não estiver carregado, `ClrCreateManagedInstance` primeiro tenta carregar v1.0.3705 do tempo de execução. Se isso falhar, ele tenta carregar a versão mais recente do tempo de execução.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também

- [Funções de hospedagem CLR preteridas](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [Hospedagem](../../../../docs/framework/unmanaged-api/hosting/index.md)
