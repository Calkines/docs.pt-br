---
title: 'Como: Classificar e filtrar dados ADO.NET com o componente BindingSource do Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: 8904eff39b7278b2a185cc5e2f738ece1e8e88e4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59306502"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>Como: Classificar e filtrar dados ADO.NET com o componente BindingSource do Windows Forms
Você pode expor a classificação e filtragem de capacidade do <xref:System.Windows.Forms.BindingSource> controlar por meio de <xref:System.Windows.Forms.BindingSource.Sort%2A> e <xref:System.Windows.Forms.BindingSource.Filter%2A> propriedades. Você pode aplicar a classificação simples quando a fonte de dados subjacente é uma <xref:System.ComponentModel.IBindingList>, e você pode aplicar a filtragem e classificação quando a fonte de dados é avançada um <xref:System.ComponentModel.IBindingListView>. O <xref:System.Windows.Forms.BindingSource.Sort%2A> propriedade requer standard [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] sintaxe: uma cadeia de caracteres que representa o nome de uma coluna de dados na fonte de dados seguido `ASC` ou `DESC` para indicar se a lista deve ser classificada em ordem crescente ou decrescente. Você pode definir a classificação avançada ou a classificação em várias colunas separando cada coluna com um separador de vírgula. O <xref:System.Windows.Forms.BindingSource.Filter%2A> propriedade usa uma expressão de cadeia de caracteres.  
  
> [!NOTE]
>  O armazenamento das informações confidenciais (tal como uma senha) dentro da cadeia de conexão pode afetar a segurança do aplicativo. O uso da Autenticação do Windows (também conhecida como segurança integrada) é uma maneira mais segura de controlar o acesso a um banco de dados. Para obter mais informações, consulte [Protegendo informações de conexão](../../data/adonet/protecting-connection-information.md).  
  
### <a name="to-filter-data-with-the-bindingsource"></a>Filtrar os dados com o BindingSource  
  
-   Defina o <xref:System.Windows.Forms.BindingSource.Filter%2A> propriedade para a expressão desejada.  
  
     No exemplo de código a seguir, a expressão é um nome de coluna seguido pelo valor que você deseja para a coluna.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>Classificar os dados com o BindingSource  
  
1. Defina as <xref:System.Windows.Forms.BindingSource.Sort%2A> propriedade para o nome da coluna que você deseja seguido por `ASC` ou `DESC` para indicar a ordem de crescente ou decrescente.  
  
2. Separe múltiplas colunas com uma vírgula.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>Exemplo  
 O exemplo de código a seguir carrega os dados da tabela Customers do banco de dados de exemplo Northwind em um <xref:System.Windows.Forms.DataGridView> controlar e filtra e classifica os dados exibidos.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Para executar este exemplo, cole o código em um formulário que contém um <xref:System.Windows.Forms.BindingSource> nomeado `BindingSource1` e uma <xref:System.Windows.Forms.DataGridView> denominada `dataGridView1`. Lidar com o <xref:System.Windows.Forms.Form.Load> eventos para o formulário e chame `InitializeSortedFilteredBindingSource` no método do manipulador de eventos de carga.  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [Como: Instalar os bancos de dados](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [Componente BindingSource](bindingsource-component.md)
