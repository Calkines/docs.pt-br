---
title: Função CreateHistoryReader
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e438006d6424866514e73119c05e8fd69d7ba62e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132256"
---
# <a name="createhistoryreader-function"></a>Função CreateHistoryReader
Cria um leitor de histórico para o arquivo especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a>Parâmetros  
 `wzFilePath`  
 [in] O caminho do arquivo.  
  
 `ppHistoryReader`  
 [out] Após a conclusão bem-sucedida, contém um ponteiro para o leitor de histórico.  
  
## <a name="return-value"></a>Valor de retorno  
 Esse método retorna códigos de erro padrão COM conforme definido em Winerror. H, além dos valores descritos na tabela a seguir.  
  
|Código de retorno|Descrição|  
|-----------------|-----------------|  
|S_OK|Indica que o método concluída com êxito.|  
|E_INVALIDARG|Indica que `wzFilePath` ou `ppHistoryReader` são definidos como uma referência nula.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Biblioteca:** Fusion  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também

- [Funções estáticas globais de fusão](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
