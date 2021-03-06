---
title: Elemento <defaultHttpCachePolicy> (Configurações de Rede)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: 20d9b92ca2bbffd6b98b8641e5cef5e567cb84cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177367"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a>\<defaultHttpCachePolicy > (configurações de rede)
Descreve se o cache de HTTP está ativo e descreve a política de cache padrão.  
  
 \<configuration>  
\<system.net>  
\<requestCaching>  
\<defaultHttpCachePolicy>  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|`maximumAge`|Especifica o intervalo de tempo máximo antes que um objeto armazenado em cache seja marcado como expirada.|  
|`maximumStale`|Especifica o tempo máximo após o tempo de atualização computada antes de um objeto armazenado em cache seja marcado como expirada.|  
|`minimumFresh`|Especifica o tempo mínimo para um objeto armazenado em cache ser considerado atualizado.|  
|`policyLevel`|Especifica se a política de cache é automática, ou se o cache é ignorado. O valor padrão é `BypassCache`.|  
  
### <a name="child-elements"></a>Elementos filho  
 Nenhum  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Controla o mecanismo de cache para solicitações de rede.|  
  
## <a name="remarks"></a>Comentários  
 O valor para o `policyLevel` atributo seja `BypassCache` ou `Default`.  
  
 Os valores para o `maximumAge`, `maximumStale`, e `minimumFresh` elementos são um intervalo de tempo explícito com um formato de *1!d*. *hh*:*mm*:*ss* (dias, horas, minutos e segundos), ou as constantes `minValue` ou `maxValue`, conforme apropriado.  
  
## <a name="configuration-files"></a>Arquivos de Configuração  
 Esse elemento pode ser usado no arquivo de configuração do aplicativo ou o arquivo de configuração de máquina (Machine. config).  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir mostra como especificar um tempo de novo mínimo de seis horas, uma hora de idade máxima de dois dias e um tempo máximo obsoleto de quatro horas.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [Esquema de configurações de rede](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
