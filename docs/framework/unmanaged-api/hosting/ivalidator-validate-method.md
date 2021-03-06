---
title: Método IValidator::Validate
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1fba06360a0c31e0a7fa3e61de9793bad14650fa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127498"
---
# <a name="ivalidatorvalidate-method"></a>Método IValidator::Validate
Valida o executável especificado portátil (PE) ou arquivo do Microsoft intermediate language (MSIL).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `veh`  
 [in] Um ponteiro para um `IVEHandler` instância que manipula erros de validação.  
  
 `pAppDomain`  
 [in] Um ponteiro para o domínio do aplicativo no qual o arquivo é carregado.  
  
 `ulFlags`  
 [in] Uma combinação bit a bit de [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) valores, que indica as validações que devem ser executadas.  
  
 `ulMaxError`  
 [in] O número máximo de erros para permitir que antes de sair da validação.  
  
 `token`  
 [in] Não usado.  
  
 `fileName`  
 [in] Uma cadeia de caracteres que especifica o nome do arquivo a ser validado.  
  
 `pe`  
 [in] Um ponteiro para o buffer de memória no qual o arquivo está armazenado.  
  
 `ulSize`  
 [in] O tamanho, em bytes, do arquivo a ser validado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** IValidator.idl, IValidator.h  
  
 **Biblioteca:** Incluído como um recurso em mscoree. dll  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
