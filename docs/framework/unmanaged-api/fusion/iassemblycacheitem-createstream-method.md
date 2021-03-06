---
title: Método IAssemblyCacheItem::CreateStream
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 380e248c8c4e3407fff868cdd9a5c63b63e50c69
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353901"
---
# <a name="iassemblycacheitemcreatestream-method"></a>Método IAssemblyCacheItem::CreateStream

Cria um fluxo com o nome especificado e o formato.

## <a name="syntax"></a>Sintaxe

```cpp
HRESULT CreateStream (
    [in]  DWORD dwFlags,
    [in]  LPCWSTR pszStreamName,
    [in]  DWORD dwFormat,
    [in]  DWORD dwFormatFlags,
    [out] IStream **ppIStream,
    [in, optional] ULARGE_INTEGER *puliMaxSize
);
```

## <a name="parameters"></a>Parâmetros

`dwFlags`\
[in] Sinalizadores definidos no Fusion.idl.

`pszStreamName`\
[in] O nome do fluxo a ser criado.

`dwFormat`\
[in] O formato do arquivo a ser transmitido.

`dwFormatFlags`\
[in] Sinalizadores de formato específicos definidos em Fusion.idl.

`ppIStream`\
[out] Um ponteiro para o endereço do retornado [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instância.

`puliMaxSize`\
[in, opcional] O tamanho máximo do fluxo referenciado pelo `ppIStream`.

## <a name="requirements"></a>Requisitos

**Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).

**Cabeçalho:** Fusion.h

**Versões do .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Consulte também

- [Interface IAssemblyCacheItem](iassemblycacheitem-interface.md)