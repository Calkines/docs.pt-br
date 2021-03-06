---
title: Cenários de aplicativos (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, learn more
- WCF Data Services, scenarios
ms.assetid: 7c82658f-e7c0-46b6-834d-6592f67ab5ea
ms.openlocfilehash: f0334f23a1b2bd454377d2f5b93e70495e693043
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212216"
---
# <a name="application-scenarios-wcf-data-services"></a>Cenários de aplicativos (WCF Data Services)

[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] dá suporte a um conjunto principal de cenários para expor e consumir dados como [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feeds. Este tópico aponta os tópicos relevantes a esses cenários.

Exponha dados relacionais de um banco de dados como um [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.
- [Quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) (Início rápido)

- [Expondo seus dados como um serviço](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)

- [Como: Criar um serviço de dados usando uma fonte de dados do ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)

Exponha classes de dados CLR arbitrárias como um feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].
- [Expondo seus dados como um serviço](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)

- [Como: Criar um serviço de dados usando o provedor de reflexão](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)

- [Provedores de Serviços de Dados](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)

Consuma um feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] em um aplicativo cliente baseado no .NET Framework.
- [Quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) (Início rápido)

- [Usando um serviço de dados em um aplicativo cliente](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md)

- [WCF Data Services Client Library](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md) (Biblioteca de clientes do WCF Data Services)

Consuma um feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] em um aplicativo cliente baseado no Silverlight.
- [WCF Data Services (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95))

- [Operações assíncronas](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)

- [Como: Associar dados do serviço de dados a controles (cliente do Silverlight)](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee681614(v=vs.103))

Consuma um feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] em um aplicativo cliente baseado no AJAX.
- [Usando um serviço de dados em um aplicativo cliente](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md)

- [OData: Convenções de URI](https://go.microsoft.com/fwlink/?LinkId=185564)

- [OData: Formato do JavaScript Object Notation (JSON)](https://go.microsoft.com/fwlink/?LinkId=185790)

Criar uma solução de dados de ponta a ponta que usa [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] para transferir dados entre cliente e servidor.
- [Quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) (Início rápido)

- [Usando um serviço de dados em um aplicativo cliente](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md)

- [WCF Data Services Client Library](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md) (Biblioteca de clientes do WCF Data Services)

Crie um aplicativo cliente baseado no .NET Framework que consuma um feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] de forma assíncrona para evitar problemas de latência no cliente.
- [Como: Executar consultas de serviço de dados assíncronos](../../../../docs/framework/data/wcf/how-to-execute-asynchronous-data-service-queries-wcf-data-services.md)

- [Operações assíncronas](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)

- [WCF Data Services (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95))

Expor e consumir um [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed com um objeto binário grande que seja acessado e alterado como um fluxo.
- [Provedor de streaming](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md)

- [Trabalhando com os dados binários](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md)

Associar [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds para controles em um aplicativo do Windows Presentation Framework (WPF).
- [Associando dados a controles](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)

- [Como: Associar dados aos elementos do Windows Presentation Foundation](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)

- [Como: Associar dados usando uma fonte de dados do projeto](../../../../docs/framework/data/wcf/how-to-bind-data-using-a-project-data-source-wcf-data-services.md)

Intercepte mensagens de entrada para o serviço de dados para executar a validação de dados e a filtragem de consultas baseada em função.
- [Como: Interceptar mensagens de serviço de dados](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md)

- [Interceptadores](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md)

Crie pontos de extremidade em um serviço de dados para habilitar comportamentos de serviço personalizados.
- [Como: Definir uma operação de serviço](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md)

- [Operações de serviço](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)

## <a name="see-also"></a>Consulte também

- [Quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) (Início rápido)
- [Recursos](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)
