---
ms.openlocfilehash: e7154919d6a09a04e650d5546feb2ae6c6cc912f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234877"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a>HttpRuntime.AppDomainAppPath gera NullReferenceException

|   |   |
|---|---|
|Detalhes|No .NET Framework 4.6.2, o tempo de execução gera <code>T:System.NullReferenceException</code> ao recuperar um valor <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> que inclui caracteres nulos. No .NET Framework 4.6.1 e versões anteriores, o tempo de execução gera <code>T:System.ArgumentNullException</code>.|
|Sugestão|Você pode fazer o seguinte para responder a essa alteração:<ul><li>Identifique o <code>T:System.NullReferenceException</code> se o aplicativo estiver sendo executado no .NET Framework 4.6.2.</li><li>Atualize para o .NET Framework 4.7, que restaura o comportamento anterior e gera <code>T:System.ArgumentNullException</code>.</li></ul>|
|Escopo|Microsoft Edge|
|Versão|4.6.2|
|Tipo|Redirecionando|
|APIs afetadas|<ul><li><xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType></li></ul>|
