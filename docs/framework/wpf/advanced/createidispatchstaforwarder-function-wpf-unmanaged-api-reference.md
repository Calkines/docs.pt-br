---
title: Função CreateIDispatchSTAForwarder (referência de API não gerenciada WPF)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: a89b29cd459060c93d5ca77bb2154e1a10b02d03
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213618"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>Função CreateIDispatchSTAForwarder (referência de API não gerenciada WPF)
Essa API dá suporte à infraestrutura do Windows Presentation Foundation (WPF) e não se destina a ser usado diretamente do seu código.  
  
 Usado pela infraestrutura do Windows Presentation Foundation (WPF) para gerenciamento de thread e do windows.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a>Parâmetros  
  
## <a name="property-valuereturn-value"></a>Valor da propriedade/valor de retorno  
 pDispatchDelegate  
 Um ponteiro para um `IDispatch` interface.  
  
 ppForwarder  
 Um ponteiro para o endereço de um `IDispatch` interface.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Ver [requisitos de sistema do .NET Framework](../../get-started/system-requirements.md).  
  
 **DLL:**  
  
 No .NET Framework 3.0 e 3.5: PresentationHostDLL.dll  
  
 No .NET Framework 4 e posterior: PresentationHost_v0400.dll  
  
 **Versão do .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Consulte também

- [Referência de API não gerenciada do WPF](wpf-unmanaged-api-reference.md)
