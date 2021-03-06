---
title: typeof – Referência de C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: f218414bf60a86b95461d747fb6c557f03bcfcb3
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2019
ms.locfileid: "57846107"
---
# <a name="typeof-c-reference"></a>typeof (Referência de C#)

Usado para obter o objeto <xref:System.Type?displayProperty=nameWithType> para um tipo. Uma expressão `typeof` usa o seguinte formato:

```csharp
System.Type type = typeof(int);
```

## <a name="remarks"></a>Comentários

Para obter o tipo de tempo de execução de uma expressão, você pode usar o método do .NET Framework <xref:System.Object.GetType%2A>, assim como no exemplo a seguir:

```csharp
int i = 0;
System.Type type = i.GetType();
```

O operador `typeof` não pode ser sobrecarregado.

O operador `typeof` também pode ser usado em tipos genéricos abertos. Tipos com mais de um parâmetro de tipo devem ter o número apropriado de vírgulas na especificação. Por exemplo, o <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWIthType> tem dois argumentos de tipo, então, você usa uma vírgula:

```csharp
Type t = typeof(System.Collection.Generic.Dictionary<,>);
```

O exemplo a seguir mostra como determinar se o tipo de retorno de um método é um <xref:System.Collections.Generic.IEnumerable%601> genérico. <xref:System.Type.GetInterface%2A?displayProperty=nameWithType> retornará `null` se o tipo de retorno não for um tipo genérico <xref:System.Collections.Generic.IEnumerable%601>.

[!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]

## <a name="example"></a>Exemplo

[!code-csharp[csrefKeywordsOperator#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#12)] 

## <a name="example"></a>Exemplo

Este exemplo usa o método <xref:System.Object.GetType%2A> para determinar o tipo que é usado para conter o resultado de um cálculo numérico. Isso depende dos requisitos de armazenamento do número resultante.

[!code-csharp[csrefKeywordsOperator#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#13)]

## <a name="c-language-specification"></a>Especificação da linguagem C#

Para obter mais informações, veja [O operador typeof](~/_csharplang/spec/expressions.md#the-typeof-operator) na [Especificação da Linguagem C#](../language-specification/index.md). A especificação da linguagem é a fonte definitiva para a sintaxe e o uso de C#.

## <a name="see-also"></a>Consulte também

- <xref:System.Type?displayProperty=nameWithType>
- [Referência de C#](../../../csharp/language-reference/index.md)
- [Guia de Programação em C#](../../../csharp/programming-guide/index.md)
- [Palavras-chave do C#](../../../csharp/language-reference/keywords/index.md)
- [is](../../../csharp/language-reference/keywords/is.md)
- [Palavras-chave do operador](../../../csharp/language-reference/keywords/operator-keywords.md)
