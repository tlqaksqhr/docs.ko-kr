---
title: "Windows Forms DataGridView 컨트롤의 성능 조정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da0171bf4fa056de2dd06c2f7e431ea55a8dab1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="1769e-102">Windows Forms DataGridView 컨트롤의 성능 조정</span><span class="sxs-lookup"><span data-stu-id="1769e-102">Performance Tuning in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1769e-103">많은 양의 데이터를 작업할 때의 `DataGridView` 신중 하 게 사용 하지 않는 한 컨트롤 많은 양의 메모리를에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1769e-103">When working with large amounts of data, the `DataGridView` control can consume a large amount of memory in overhead, unless you use it carefully.</span></span> <span data-ttu-id="1769e-104">제한 된 메모리와 클라이언트에 메모리가 많이 있는 기능을 방지 하 여 이러한 오버 헤드 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1769e-104">On clients with limited memory, you can avoid some of this overhead by avoiding features that have a high memory cost.</span></span> <span data-ttu-id="1769e-105">또한 데이터 유지 관리의 일부 또는 전부를 관리할 수 있습니다와 가상 모드를 사용 하 여 메모리 사용 시나리오에 대 한 사용자 지정 하기 위해 직접 검색 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="1769e-105">You can also manage some or all of the data maintenance and retrieval tasks yourself using virtual mode in order to customize the memory usage for your scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1769e-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="1769e-106">In This Section</span></span>  
 [<span data-ttu-id="1769e-107">Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="1769e-107">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="1769e-108">사용 하는 방법에 설명 된 `DataGridView` 많은 양의 데이터를 작업할 때는 불필요 한 메모리 사용량 및 성능 저하를 방지 하는 방법에 대 한 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1769e-108">Describes how to use the `DataGridView` control in a way that avoids unnecessary memory usage and performance penalties when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="1769e-109">Windows Forms DataGridView 컨트롤의 가상 모드</span><span class="sxs-lookup"><span data-stu-id="1769e-109">Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="1769e-110">가상 모드 보완 하거나 바꿀 표준 데이터 바인딩 메커니즘을 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1769e-110">Describes how to use virtual mode to supplement or replace the standard data-binding mechanism.</span></span>  
  
 [<span data-ttu-id="1769e-111">연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현</span><span class="sxs-lookup"><span data-stu-id="1769e-111">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 <span data-ttu-id="1769e-112">여러 개의 가상 모드 이벤트에 대 한 처리기를 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1769e-112">Describes how to implement handlers for several virtual-mode events.</span></span> <span data-ttu-id="1769e-113">또한 행 수준 rollback 및 commit 사용자 편집에 대 한 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1769e-113">Also demonstrates how to implement row-level rollback and commit for user edits.</span></span>  
  
 [<span data-ttu-id="1769e-114">Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현</span><span class="sxs-lookup"><span data-stu-id="1769e-114">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 <span data-ttu-id="1769e-115">필요할 때에는 표시할 사용 가능한 클라이언트 메모리에 저장할 수 있는 것 보다 더 많은 데이터가 있는 경우 데이터를 로드 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1769e-115">Describes how to load data on demand, which is useful when you have more data to display than the available client memory can store.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1769e-116">참조</span><span class="sxs-lookup"><span data-stu-id="1769e-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="1769e-117"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1769e-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <span data-ttu-id="1769e-118">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1769e-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1769e-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1769e-119">See Also</span></span>  
 [<span data-ttu-id="1769e-120">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1769e-120">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="1769e-121">Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드</span><span class="sxs-lookup"><span data-stu-id="1769e-121">Data Display Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
