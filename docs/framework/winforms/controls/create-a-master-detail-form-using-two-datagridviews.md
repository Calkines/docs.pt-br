---
title: 'Como: Criar um formulário mestre / detalhes usando dois controles de Windows Forms DataGridView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], creating
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
ms.openlocfilehash: ccd9354d623cf1b452bc3890b7fd9a5248cb69c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088789"
---
# <a name="how-to-create-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Como: Criar um formulário mestre/de detalhes usando dois controles DataGridView do Windows Forms
O exemplo de código a seguir cria um formulário mestre/detalhes usando dois <xref:System.Windows.Forms.DataGridView> controles associados a dois <xref:System.Windows.Forms.BindingSource> componentes. A fonte de dados é um <xref:System.Data.DataSet> que contém o `Customers` e `Orders` tabelas do banco de dados de exemplo Northwind do SQL Server juntamente com um <xref:System.Data.DataRelation> que relaciona as duas as `CustomerID` coluna.  
  
 Uma <xref:System.Windows.Forms.BindingSource> está associado ao pai `Customers` tabela no conjunto de dados. Esses dados são exibidos no mestre <xref:System.Windows.Forms.DataGridView> controle. O outro <xref:System.Windows.Forms.BindingSource> está associado ao primeiro conector de dados. O <xref:System.Windows.Forms.BindingSource.DataMember%2A> propriedade da segunda <xref:System.Windows.Forms.BindingSource> é definido como o <xref:System.Data.DataRelation> nome. Isso faz com que os detalhes associados <xref:System.Windows.Forms.DataGridView> controle para exibir as linhas do filho `Orders` tabela que correspondem à linha atual no mestre <xref:System.Windows.Forms.DataGridView> controle.  
  
 Para obter uma explicação completa sobre este exemplo de código, consulte [passo a passo: Criando um formulário mestre/detalhes usando dois Windows Forms a controles DataGridView](creating-a-master-detail-form-using-two-datagridviews.md).  
  
## <a name="example"></a>Exemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Este exemplo requer:  
  
 Referências aos assemblies System, System.Data, System.Windows.Forms e System.XML.  
  
-   Para obter informações sobre como compilar este exemplo da linha de comando para o Visual Basic ou Visual c#, consulte [compilando da linha de comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) ou [criação de linha de comando com csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Você também pode criar este exemplo no Visual Studio colando o código em um novo projeto.  
  
## <a name="net-framework-security"></a>Segurança do .NET Framework  
 O armazenamento das informações confidenciais (tal como uma senha) dentro da cadeia de conexão pode afetar a segurança do aplicativo. O uso da Autenticação do Windows (também conhecida como segurança integrada) é uma maneira mais segura de controlar o acesso a um banco de dados. Para obter mais informações, consulte [Protegendo informações de conexão](../../data/adonet/protecting-connection-information.md).  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Passo a passo: Criando um formulário mestre/detalhes usando dois controles de Windows Forms DataGridView](creating-a-master-detail-form-using-two-datagridviews.md)
- [Exibindo dados no controle DataGridView do Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Protegendo informações de conexão](../../data/adonet/protecting-connection-information.md)
