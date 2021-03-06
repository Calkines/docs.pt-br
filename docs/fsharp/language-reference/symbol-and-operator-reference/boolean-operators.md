---
title: Operadores boolianos
description: Saiba mais sobre os operadores boolianos que estão disponíveis no F# linguagem de programação.
ms.date: 05/16/2016
ms.openlocfilehash: 5353b6ec6a0bd610f3446761a1d28f01f0403302
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612732"
---
# <a name="boolean-operators"></a>Operadores boolianos

Este tópico descreve o suporte para operadores boolianos no F# idioma.

## <a name="summary-of-boolean-operators"></a>Resumo de operadores boolianos

A tabela a seguir resume os operadores boolianos que estão disponíveis no F# idioma. O único tipo com suporte desses operadores é o `bool` tipo.

|Operador|Descrição|
|--------|-----------|
|`not`|Boleana|
|<code>&#124;&#124;</code>|Booliano OR|
|`&&`|Booliano AND|

Executam o booliano e e/ou operadores *avaliação curto-circuito*, ou seja, eles avaliar a expressão à direita do operador somente quando for necessário determinar o resultado geral da expressão. A segunda expressão do `&&` operador é avaliado somente se a primeira expressão é avaliada como `true`; a segunda expressão do `||` operador é avaliado somente se a primeira expressão é avaliada como `false`.

## <a name="see-also"></a>Consulte também

- [Operadores Bit a Bit](bitwise-operators.md)
- [Operadores Aritméticos](arithmetic-operators.md)
- [Referência de Símbolos e Operadores](index.md)