---
title: 'Como: Classificar resultados de consulta usando LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- sorting query results, multiple columns
- sorting data [Visual Basic]
- sorting data [LINQ in Visual Basic]
- sorting query results [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], sorting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 07a4584d-9fd8-4a1d-b7d9-ccf2efa5c84e
ms.openlocfilehash: d2114e908077ec947164a28f48841282abefda2e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59301211"
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a>Como: Classificar resultados de consulta usando LINQ (Visual Basic)
Consulta integrada à linguagem (LINQ) facilita o acesso às informações de banco de dados e executar consultas.  
  
 O exemplo a seguir mostra como criar um novo aplicativo que executa consultas em um banco de dados do SQL Server e classifica os resultados por vários campos usando o `Order By` cláusula. A ordem de classificação para cada campo pode ser ordem crescente ou decrescente. Para obter mais informações, consulte [cláusula Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Os exemplos neste tópico usam o banco de dados de exemplo Northwind. Se você não tiver esse banco de dados no computador de desenvolvimento, você pode baixá-lo do Microsoft Download Center. Para obter instruções, consulte [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Para criar uma conexão para um banco de dados  
  
1. No Visual Studio, abra **Gerenciador de servidores**/**Database Explorer** clicando **Server Explorer**/**banco de dados Explorer** sobre o **exibição** menu.  
  
2. Clique com botão direito **conexões de dados** na **Gerenciador de servidores**/**Database Explorer** e, em seguida, clique em **Adicionar Conexão**.  
  
3. Especifique uma conexão válida para o banco de dados de exemplo Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Para adicionar um projeto que contém um arquivo LINQ to SQL  
  
1. No Visual Studio, no menu **Arquivo**, aponte para **Novo** e clique em **Projeto**. Selecione Visual Basic **aplicativo do Windows Forms** como o tipo de projeto.  
  
2. No menu **Projeto**, clique em **Adicionar Novo Item**. Selecione o **Classes LINQ to SQL** modelo de item.  
  
3. Dê o nome `northwind.dbml` para o arquivo. Clique em **Adicionar**. O Object Relational Designer (O/R Designer) é aberto para o arquivo Northwind dbml.  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>Para adicionar tabelas de consulta para o O/R Designer  
  
1. Na **Gerenciador de servidores**/**Gerenciador de banco de dados**, expanda a conexão ao banco de dados Northwind. Expanda o **tabelas** pasta.  
  
     Se você tiver fechado o O/R Designer, você poderá reabri-lo clicando duas vezes no arquivo dbml que você adicionou anteriormente.  
  
2. Clique na tabela clientes e arraste-o no painel esquerdo do designer. Clique na tabela Orders e arraste-o no painel esquerdo do designer.  
  
     O designer cria novos `Customer` e `Order` objetos para o seu projeto. Observe que o designer automaticamente detecta as relações entre as tabelas e cria propriedades filhas para objetos relacionados. Por exemplo, o IntelliSense mostrará que o `Customer` objeto tem um `Orders` propriedade para todos os pedidos relacionados a esse cliente.  
  
3. Salve suas alterações e feche o designer.  
  
4. Salve seu projeto.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Para adicionar código para consultar o banco de dados e exibir os resultados  
  
1. Dos **caixa de ferramentas**, arraste um <xref:System.Windows.Forms.DataGridView> controle para o formulário do Windows padrão para seu projeto, Form1.  
  
2. Clique duas vezes em Form1 para adicionar código para o `Load` evento do formulário.  
  
3. Quando você adicionar tabelas ao Designer relacional de objetos, o designer adicionará um <xref:System.Data.Linq.DataContext> objeto ao seu projeto. Este objeto contém o código que você deve ter para acessar essas tabelas e para acessar objetos individuais e coleções para cada tabela. O <xref:System.Data.Linq.DataContext> objeto para seu projeto é nomeado com base no nome do seu arquivo. dbml. Para este projeto, o <xref:System.Data.Linq.DataContext> objeto é nomeado `northwindDataContext`.  
  
     Você pode criar uma instância da <xref:System.Data.Linq.DataContext> no seu código e consultar as tabelas especificadas pelo Designer relacional de objetos.  
  
     Adicione o seguinte código para o `Load` eventos para consultar as tabelas que são expostas como propriedades de seu contexto de dados e classificar os resultados. A consulta classifica os resultados pelo número de pedidos de clientes, em ordem decrescente. Os clientes que têm o mesmo número de pedidos são ordenados pelo nome da empresa em ordem (o padrão) crescente.  
  
     [!code-vb[VbLINQToSQLHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form4.vb#10)]  
  
4. Pressione F5 para executar seu projeto e exibir os resultados.  
  
## <a name="see-also"></a>Consulte também

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Consultas](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Métodos DataContext (Designer Relacional de Objetos)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
