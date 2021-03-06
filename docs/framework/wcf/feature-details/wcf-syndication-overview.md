---
title: Visão geral de sindicalização do WCF
ms.date: 03/30/2017
ms.assetid: af6d4c39-e5e8-4099-aee6-5261feff9107
ms.openlocfilehash: ef62c4460ff5dd4890de174afda671facee97f2e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189815"
---
# <a name="wcf-syndication-overview"></a>Visão geral de sindicalização do WCF
Windows Communication Foundation (WCF) oferece suporte para expor feeds de sindicalização de um serviço WCF. Sindicalização é um mecanismo de integração de aplicativos no qual um servidor expõe alguns dados de aplicativo em um formato interoperável, conhecido como um feed. Um feed é uma coleção de dados de aplicativo que consiste em alguns metadados de nível de feed (título, autor, URL e outros metadados) e uma série de itens de feed. Dentro do feed, os itens do feed são geralmente temporal em ordem cronológica inversa. Um item de feed consiste em um conjunto padrão de metadados de nível de item (title, URL, data de criação, categoria e outros metadados de nível de item) e uma quantidade arbitrária de dados específicos do aplicativo. Os dois tipos mais comuns de feeds de agregação são RSS Really Simple Syndication () 2.0 e Atom 1.0, sendo que ambos têm suporte pelo WCF.  
  
## <a name="object-model"></a>Modelo de objeto  
 O WCF define um conjunto de classes específicas de agregação que permitem trabalhar com feeds, itens de feed e os metadados relacionados de forma independente de formato: <xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem>, <xref:System.ServiceModel.Syndication.SyndicationPerson>, <xref:System.ServiceModel.Syndication.SyndicationLink>e outras classes específicas de distribuição. O WCF também define classes de infraestrutura que aproveitam o modelo de programação do WCF REST para fornecer suporte de sindicalização incluindo: <xref:System.ServiceModel.Syndication.Atom10FeedFormatter>, e <xref:System.ServiceModel.Syndication.Rss20FeedFormatter>. As classes de formatador do feed suportam serializando o modelo de objeto e para RSS 2.0 e Atom 1.0.  
  
## <a name="scenarios"></a>Cenários  
 Um uso comum de hoje em dia de distribuição é blogs, onde o autor do blog publica periodicamente algum tipo de informações. Isso pode ser texto, imagens, áudio ou outros tipos de informações. Muitos jornais e revistas também publicam histórias de notícias ou em artigos usando a distribuição. Ao assinar esse feed, um usuário pode manter atualizado com todas as novas informações provenientes de tais sites. Embora a distribuição é mais comumente associada com blogs e editores, ele pode ser usado com qualquer aplicativo que expõe uma coleção de informações; Por exemplo, um banco de dados de bug que você quer expor usando um distribuição de alimentação. Você pode criar um serviço WCF que expõe uma operação chamada `CodeDefects`. Essa operação pode levar a um parâmetro que especifica o endereço de email da pessoa cujos bugs que você deseja recuperar. Um cliente pode usar a URL a seguir para chamar a operação: `http://someserver/bugDatabase/CodeDefects?user=johndoe`.  
  
## <a name="syndication-formats"></a>Formatos de distribuição  
 A plataforma de sindicalização do WCF dá suporte a RSS 2.0 e Atom 1.0.  
  
## <a name="see-also"></a>Consulte também

- [Modelo de programação HTTP Web do WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
