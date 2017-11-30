---
title: "방법: 행 템플릿을 사용하여 Windows Forms DataGridView 컨트롤에서 행 사용자 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bed37026578c739bdc07beb039ec83f091587535
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="9587c-102">방법: 행 템플릿을 사용하여 Windows Forms DataGridView 컨트롤에서 행 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="9587c-102">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="9587c-103"><xref:System.Windows.Forms.DataGridView> 컨트롤 사용 하 여 행 템플릿을 기반으로 데이터 바인딩을 통해 또는 호출 하는 경우 컨트롤에 추가 하는 모든 행에 대 한는 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> 기존 행을 지정 하지 않고 메서드.</span><span class="sxs-lookup"><span data-stu-id="9587c-103">The <xref:System.Windows.Forms.DataGridView> control uses the row template as a basis for all rows that it adds to the control either through data binding or when you call the <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> method without specifying an existing row to use.</span></span>  
  
 <span data-ttu-id="9587c-104">행 템플릿을 사용 모양 및 동작 보다는 행에 대 한 제어 강화는 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9587c-104">The row template gives you greater control over the appearance and behavior of rows than the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property provides.</span></span> <span data-ttu-id="9587c-105">행 템플릿을 사용 하 여 설정할 수 있습니다 <xref:System.Windows.Forms.DataGridViewRow> 속성을 포함 하 여 <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="9587c-105">With the row template, you can set any <xref:System.Windows.Forms.DataGridViewRow> properties, including <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span></span>  
  
 <span data-ttu-id="9587c-106">특정 결과를 얻을 행 템플릿을 사용 해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9587c-106">There are some situations where you must use the row template to achieve a particular effect.</span></span> <span data-ttu-id="9587c-107">예를 들어에 행 높이 정보를 저장할 수 없습니다는 <xref:System.Windows.Forms.DataGridViewCellStyle>, 하므로 모든 행에서 사용 하는 기본 높이 변경 하려면 행 템플릿을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9587c-107">For example, row height information cannot be stored in a <xref:System.Windows.Forms.DataGridViewCellStyle>, so you must use a row template to change the default height used by all rows.</span></span> <span data-ttu-id="9587c-108">행 템플릿을도 유용에서 파생 된 사용자 고유의 클래스를 만들 때 <xref:System.Windows.Forms.DataGridViewRow> 컨트롤에 새 행을 추가할 때 사용 되는 사용자 지정 형식 중이 고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9587c-108">The row template is also useful when you create your own classes derived from <xref:System.Windows.Forms.DataGridViewRow> and you want your custom type used when new rows are added to the control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9587c-109">행 템플릿은 행을 추가 하는 경우에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9587c-109">The row template is used only when rows are added.</span></span> <span data-ttu-id="9587c-110">행 템플릿을 변경 하 여 기존 행을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9587c-110">You cannot change existing rows by changing the row template.</span></span>  
  
### <a name="to-use-the-row-template"></a><span data-ttu-id="9587c-111">행 템플릿을 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="9587c-111">To use the row template</span></span>  
  
-   <span data-ttu-id="9587c-112">검색 된 개체의 속성을 설정는 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9587c-112">Set properties on the object retrieved from the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9587c-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="9587c-113">Compiling the Code</span></span>  
 <span data-ttu-id="9587c-114">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9587c-114">This example requires:</span></span>  
  
-   <span data-ttu-id="9587c-115">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9587c-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="9587c-116"><xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="9587c-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9587c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9587c-117">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="9587c-118">Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="9587c-118">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="9587c-119">Windows Forms DataGridView 컨트롤의 셀 스타일</span><span class="sxs-lookup"><span data-stu-id="9587c-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
