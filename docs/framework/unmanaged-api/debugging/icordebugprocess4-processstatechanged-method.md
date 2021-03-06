---
title: Método ICorDebugProcess4::ProcessStateChanged
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: b77dd1277e7d23729f30d9d495c5417055a22759
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378971"
---
# <a name="icordebugprocess4processstatechanged-method"></a>Método ICorDebugProcess4::ProcessStateChanged

Notifica o pipeline ICorDebug que fora do depurador de processo está continuando a execução do depurado.

## <a name="syntax"></a>Sintaxe

```
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>Parâmetros

 `eChange`\
[in] Um membro do [enumeração CorDebugStateChange](cordebugstatechange-enumeration.md) que descreve uma alteração no estado de execução do processo.

## <a name="remarks"></a>Comentários

O método fornecido é parte do `ICorDebugProcess4` de interface e corresponde ao slot de quarto da tabela de método virtual.

## <a name="requirements"></a>Requisitos

 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).

 **Cabeçalho:** Nenhum

 **Biblioteca:** Nenhum
 
 **Versões do .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Consulte também

- [Interface ICorDebugProcess4](icordebugprocess4-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
- [Depuração](index.md)