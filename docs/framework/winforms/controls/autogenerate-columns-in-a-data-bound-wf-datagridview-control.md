---
title: "방법: 데이터 바인딩된 Windows Forms DataGridView 컨트롤에서 열 자동 생성"
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
helpviewer_keywords:
- data grids [Windows Forms], autogenerating columns
- columns [Windows Forms], autogenerating
- DataGridView control [Windows Forms], data-bound columns
ms.assetid: 699f6f9e-6aa5-4811-902b-6a2c57dec7d6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 18d54da2c24d592b6fb6b53be10824c85682f9db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-autogenerate-columns-in-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="1e0ad-102">방법: 데이터 바인딩된 Windows Forms DataGridView 컨트롤에서 열 자동 생성</span><span class="sxs-lookup"><span data-stu-id="1e0ad-102">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1e0ad-103">다음 코드 예제에 바인딩된 데이터 원본에서 열을 표시 하는 방법을 보여 줍니다는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ad-103">The following code example demonstrates how to display columns from a bound data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="1e0ad-104">경우는 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> 속성 값은 `true` (기본값) 이면는 <xref:System.Windows.Forms.DataGridViewColumn> 데이터 원본 테이블의 각 열에 대해 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ad-104">When the <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> property value is `true` (the default), a <xref:System.Windows.Forms.DataGridViewColumn> is created for each column in the data source table.</span></span>  
  
 <span data-ttu-id="1e0ad-105">경우는 <xref:System.Windows.Forms.DataGridView> 컨트롤에 이미 열 설정 하는 경우는 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> 속성, 기존의 바인딩된 열 데이터 원본에 열이 비교 되며 일치 하는 항목이 때마다 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ad-105">If the <xref:System.Windows.Forms.DataGridView> control already has columns when you set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property, the existing bound columns are compared to the columns in the data source and preserved whenever there is a match.</span></span> <span data-ttu-id="1e0ad-106">바인딩되지 않은 열은 항상 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ad-106">Unbound columns are always preserved.</span></span> <span data-ttu-id="1e0ad-107">바인딩된 열을 일치 하는 데이터 소스에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ad-107">Bound columns for which there is no match in the data source are removed.</span></span> <span data-ttu-id="1e0ad-108">컨트롤에서 일치 하지 않는 데이터 원본의 열을 새로 생성할 <xref:System.Windows.Forms.DataGridViewColumn> 의 끝에 추가 되는 개체는 <xref:System.Windows.Forms.DataGridView.Columns%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ad-108">Columns in the data source for which there is no match in the control generate new <xref:System.Windows.Forms.DataGridViewColumn> objects, which are added to the end of the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e0ad-109">예</span><span class="sxs-lookup"><span data-stu-id="1e0ad-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#020](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#020)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#020](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#020)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1e0ad-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="1e0ad-110">Compiling the Code</span></span>  
 <span data-ttu-id="1e0ad-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ad-111">This example requires:</span></span>  
  
-   <span data-ttu-id="1e0ad-112">`customersDataGridView`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1e0ad-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView`.</span></span>  
  
-   <span data-ttu-id="1e0ad-113">A <xref:System.Data.DataSet> 라는 개체 `customersDataSet` 이라는 테이블이 있는 `Customers`합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ad-113">A <xref:System.Data.DataSet> object named `customersDataSet` that has a table named `Customers`.</span></span>  
  
-   <span data-ttu-id="1e0ad-114"><xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> 및 <xref:System.Xml?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="1e0ad-114">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e0ad-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e0ad-115">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="1e0ad-116">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="1e0ad-116">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="1e0ad-117">방법: 자동으로 생성된 열을 Windows Forms DataGridView 컨트롤에서 제거</span><span class="sxs-lookup"><span data-stu-id="1e0ad-117">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/remove-autogenerated-columns-from-a-wf-datagridview-control.md)
