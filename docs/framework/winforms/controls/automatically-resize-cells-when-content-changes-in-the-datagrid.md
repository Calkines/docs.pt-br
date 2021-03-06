---
title: 'Como: Redimensionar automaticamente células quando o conteúdo é alterado no controle DataGridView do Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells automatically
- cells [Windows Forms], resizing automatically
- DataGridView control [Windows Forms], resizing cells
ms.assetid: 1d68934d-a04c-4b12-9e66-c856c6828131
ms.openlocfilehash: 7acd7777ede726b9dfed2b821e4248a0ebf7797f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182488"
---
# <a name="how-to-automatically-resize-cells-when-content-changes-in-the-windows-forms-datagridview-control"></a>Como: Redimensionar automaticamente células quando o conteúdo é alterado no controle DataGridView do Windows Forms
Você pode configurar o <xref:System.Windows.Forms.DataGridView> de controle para redimensionar suas linhas, colunas e cabeçalhos automaticamente sempre que alterações de conteúdo, para que as células sejam sempre grandes o suficiente para exibir seus valores sem recorte.  
  
 Você tem várias opções para restringir as células que são usadas para determinar os novos tamanhos. Por exemplo, você pode configurar o controle para redimensionar automaticamente a largura de suas colunas com base apenas nos valores de linhas atualmente exibidas. Com isso, você pode evitar a ineficiência ao trabalhar com um grande número de linhas, embora nesse caso, você talvez queira usar métodos de dimensionamento como <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> para ajustar os tamanhos em momentos de sua escolha.  
  
 Para obter mais informações sobre redimensionamento automático, consulte [Opções de redimensionamento no controle DataGridView nos Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md).  
  
 O exemplo de código a seguir demonstra as opções disponíveis para o redimensionamento automático.  
  
## <a name="example"></a>Exemplo  
 [!code-cpp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CPP/autosizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CS/autosizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/VB/autosizing.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Este exemplo requer:  
  
-   Referências aos assemblies System, System.Drawing e System.Windows.Forms.  
  
-   Para obter informações sobre como compilar este exemplo da linha de comando para o Visual Basic ou Visual c#, consulte [compilando da linha de comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) ou [criação de linha de comando com csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Você também pode criar este exemplo no Visual Studio colando o código em um novo projeto.
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [Redimensionando colunas e linhas no controle DataGridView dos Windows Forms](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md) (Opções de dimensionamento no controle DataGridView dos Windows Forms)
- [Como: Redimensionar de forma programática as células para ajustar o conteúdo no controle DataGridView dos Windows Forms](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)
