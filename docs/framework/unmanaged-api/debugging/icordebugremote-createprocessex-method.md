---
title: Método ICorDebugRemote::CreateProcessEx
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.CreateProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a38812803127857281f9766fa3ed551971ec0330
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093509"
---
# <a name="icordebugremotecreateprocessex-method"></a>Método ICorDebugRemote::CreateProcessEx
Inicia um processo em um computador remoto sob o depurador.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT CreateProcessEx (  
    [in]  ICorDebugRemoteTarget*      pRemoteTarget,  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess**          ppProcess  
);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `pRemoteTarget`  
 [in] Ponteiro para um [Interface ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md). Usado para determinar o computador remoto no qual o processo será iniciado.  
  
 `lpApplicationName`  
 [in] Ponteiro para uma cadeia de caracteres terminada em nulo que especifica o módulo a ser executado, o processo iniciado. O módulo é executado no contexto de segurança do processo de chamada.  
  
 `lpCommandLine`  
 [in] Ponteiro para uma cadeia de caracteres terminada em nulo que especifica a linha de comando a ser executado, o processo iniciado.  
  
 `lpProcessAttributes`  
 [in] Não utilizado para a depuração remota.  
  
 `lpThreadAttributes`  
 [in] Não utilizado para a depuração remota.  
  
 `bInheritHandles`  
 [in] Não utilizado para a depuração remota.  
  
 `dwCreationFlags`  
 [in] Não utilizado para a depuração remota.  
  
 `lpEnvironment`  
 [in] Ponteiro para um bloco de ambiente para o novo processo.  
  
 `lpCurrentDirectory`  
 [in] Ponteiro para uma cadeia de caracteres terminada em nulo que especifica o caminho completo para o diretório atual para o processo. Se esse parâmetro for nulo, o novo processo terá a mesma unidade atual e o diretório como o processo de chamada.  
  
 `lpStartupInfo`  
 [in] Não utilizado para a depuração remota.  
  
 `lpProcessInformation`  
 [in] Não utilizado para a depuração remota.  
  
 `debuggingFlags`  
 [in] Não utilizado para a depuração remota.  
  
 `ppProcess`  
 [out] Um ponteiro para o endereço de um objeto de "ICorDebugProcess Interface" que representa o processo.  
  
## <a name="return-value"></a>Valor de retorno  
 S_OK  
 Iniciado com êxito o processo no computador remoto e retornado uma "Interface ICorDebugProcess" para depuração.  
  
 E_FAIL (ou outros códigos de retorno e _)  
 Não é possível iniciar o processo no computador remoto e retornar uma "ICorDebugProcess Interface" para depuração.  
  
## <a name="remarks"></a>Comentários  
 Não há suporte para a depuração de modo misto no Silverlight.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET framework:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>Consulte também

- [Interface ICorDebugRemote](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [Interface ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [Depurando interfaces](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
