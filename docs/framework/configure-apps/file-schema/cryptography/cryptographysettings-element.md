---
title: Elemento <cryptographySettings>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
ms.openlocfilehash: ec3a5a73caa901a21e22dbec7500af9153e01ef4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164132"
---
# <a name="cryptographysettings-element"></a>\<cryptographySettings > elemento
Contém configurações de criptografia.  
  
 \<configuration>  
\<mscorlib>  
\<cryptographySettings>  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
 nenhuma.  
  
### <a name="child-elements"></a>Elementos filho  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<cryptoNameMapping>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|Contém mapeamentos de classes para nomes amigáveis.|  
|[\<oidMap>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|Contém mapeamentos OID (identificador) de objeto do ASN.1 para classes.|  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|`configuration`|O elemento raiz em cada arquivo de configuração usado pelos aplicativos do Common Language Runtime e .NET Framework.|  
|`mscorlib`|Contém o `cryptographySettings` elemento.|  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir mostra como usar o  **\<cryptographySettings >** elemento para conter os mapeamentos de nome de criptografia e mapeamentos OID. Este exemplo configura o tempo de execução para que <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> retorna um `MyHashClass` objeto e o `MyCryptoClass` é mapeado para o identificador de objeto 1.3.36.2.1 de classe.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte também

- [Esquema de arquivos de configuração](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Esquema de configurações de criptografia](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [Serviços criptográficos](../../../../../docs/standard/security/cryptographic-services.md)
