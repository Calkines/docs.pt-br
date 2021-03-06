---
title: Estrutura DacpReJitData
ms.date: 02/01/2019
api.name:
- DacpReJitData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpReJitData Structure
helpviewer.keywords:
- DacpReJitData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: a2850add9acb2f7c5297ac6956e349c9277be291
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122792"
---
# <a name="dacprejitdata-structure"></a>Estrutura DacpReJitData

Define as informações básicas sobre um determinado método instrumentados pelo criador de perfil.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxe

```
struct MSLAYOUT DacpReJitData
{
    enum Flags
    {
        kUnknown,
        kRequested,
        kActive,
        kReverted,
    };

    CLRDATA_ADDRESS                 rejitID;
    Flags                           flags;
    CLRDATA_ADDRESS                 NativeCodeAddr;
};
```

## <a name="members"></a>Membros

| Membro           | Descrição                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | O número de revisão do ReJit para um método.                                                          |
| `flags`          | Um sinalizador que indica o estado atual de instrumentação do ReJit do método para a versão especificada. |
| `NativeCodeAddr` | O endereço básico da implementação de rejitted do método.                                         |

## <a name="remarks"></a>Comentários

Essa estrutura reside dentro do tempo de execução e não é exposta por meio de todos os cabeçalhos ou arquivos de biblioteca. Para usá-lo, defina a estrutura conforme especificado acima. A estrutura também deve ser definida usando `ms_struct` de remessa se não estiver usando os compiladores Microsoft.

## <a name="requirements"></a>Requisitos
**Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Cabeçalho:** Nenhum  
**Biblioteca:** Nenhum  
**Versões do .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Consulte também

- [Depuração](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Estruturas de depuração](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
