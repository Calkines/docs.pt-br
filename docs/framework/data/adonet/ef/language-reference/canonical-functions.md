---
title: Funções canônicas
ms.date: 03/30/2017
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
ms.openlocfilehash: 380c1dbcf86d8bbb844c2b226697d72d00c3e81a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202931"
---
# <a name="canonical-functions"></a>Funções canônicas
Essa seção discute as funções canônicas que têm suporte por todos os provedores de dados e podem ser usadas por todas as tecnologias de consulta. As funções canônicas não podem ser estendidas por um provedor.  
  
 Essas funções canônicas serão convertidas à funcionalidade da fonte de dados correspondente para o provedor. Isso permite as invocações da função expressas em um formulário comum nas fontes de dados.  
  
 Como essas funções canônicas são independentes das fontes de dados, o argumento e os tipos de retorno de funções canônicas são definidos em termos de tipos no modelo conceitual. Porém, algumas fontes de dados podem não dar suporte a todos os tipos no modelo conceitual.  
  
 Quando as funções canônicas são usadas em uma consulta do [!INCLUDE[esql](../../../../../../includes/esql-md.md)], a função apropriada será chamada na fonte de dados.  
  
 Todas as funções canônicas têm as condições de erro e o comportamento de entrada nulo especificadas explicitamente. Os provedores de repositório devem estar de acordo com esse comportamento, mas o [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] não impõem esse comportamento.  
  
 Para cenários LINQ, consultas em relação a [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] envolvem mapeamento de métodos CLR para métodos na fonte de dados subjacente. Os métodos CLR mapeiam para funções canônicas, de modo que um conjunto específico de métodos mapeará corretamente, independentemente da fonte de dados.  
  
## <a name="canonical-functions-namespace"></a>Namespace de funções canônicas  
 O namespace para a função canônica é <xref:System.Data.Metadata.Edm>. O namespace <xref:System.Data.Metadata.Edm> é incluído automaticamente em todas as consultas. No entanto, se outro namespace for importado e contiver uma função com o mesmo nome de uma função canônica (no namespace <xref:System.Data.Metadata.Edm>), você deverá especificar o namespace.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Funções canônicas agregadas](../../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)  
 Discute funções canônicas de agregação de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Funções canônicas matemáticas](../../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)  
 Discute funções canônicas matemáticas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Funções canônicas de cadeia de caracteres](../../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)  
 Discute funções canônicas de cadeias de caracteres de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Funções canônicas de data e hora](../../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)  
 Discute funções canônicas de data e hora de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Funções canônicas bit a bit](../../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)  
 Discute funções canônicas bit a bit de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Funções espaciais](../../../../../../docs/framework/data/adonet/ef/language-reference/spatial-functions.md)  
 Discute funções canônicas espaciais de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Outras funções canônicas](../../../../../../docs/framework/data/adonet/ef/language-reference/other-canonical-functions.md)  
 Discute as funções não classificadas como bit a bit, data/hora, cadeia de caracteres, matemática ou de agregação.  
  
## <a name="see-also"></a>Consulte também

- [Visão geral do Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [Referência de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Mapeamento de funções canônicas de modelo conceitual para o SQL Server](../../../../../../docs/framework/data/adonet/ef/conceptual-model-canonical-to-sql-server-functions-mapping.md)
- [Funções definidas pelo usuário](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)
