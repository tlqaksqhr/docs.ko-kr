---
title: "방법: 모눈 간 크기 조정 속성 공유"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8f80d93f9625ff962a3e3fab1f6647678ecf32f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-share-sizing-properties-between-grids"></a><span data-ttu-id="0fbd8-102">방법: 모눈 간 크기 조정 속성 공유</span><span class="sxs-lookup"><span data-stu-id="0fbd8-102">How to: Share Sizing Properties Between Grids</span></span>
<span data-ttu-id="0fbd8-103">이 예에서는 열 크기 조정 데이터를 공유 하는 방법을 보여 줍니다. and 간의 행 <xref:System.Windows.Controls.Grid> 일관 된 크기 조정 유지 하기 위해 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0fbd8-103">This example shows how to share the sizing data of columns and rows between <xref:System.Windows.Controls.Grid> elements in order to keep sizing consistent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fbd8-104">예</span><span class="sxs-lookup"><span data-stu-id="0fbd8-104">Example</span></span>  
 <span data-ttu-id="0fbd8-105">다음 예제에서는 두 개의 <xref:System.Windows.Controls.Grid> 부모의 자식 요소로 요소 <xref:System.Windows.Controls.DockPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="0fbd8-105">The following example introduces two <xref:System.Windows.Controls.Grid> elements as child elements of a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="0fbd8-106"><xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> 연결 된 속성의 <xref:System.Windows.Controls.Grid> 부모에 정의 된 <xref:System.Windows.Controls.DockPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="0fbd8-106">The <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> attached property of <xref:System.Windows.Controls.Grid> is defined on the parent <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="0fbd8-107">이 예제에서는 두 개를 사용 하 여 속성 값을 조작 <xref:System.Windows.Controls.Button> 요소; 부울 속성 값의 각 요소 하나 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0fbd8-107">The example manipulates the property value by using two <xref:System.Windows.Controls.Button> elements; each element represents one of the Boolean property values.</span></span> <span data-ttu-id="0fbd8-108">경우는 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> 속성 값으로 설정 됩니다 `true`의 각 행 이나 열 멤버는 <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> 행 또는 열의 내용에 관계 없이 크기 조정 정보를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fbd8-108">When the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> property value is set to `true`, each column or row member of a <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> shares sizing information, regardless of the content of a row or column.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="0fbd8-109">...</span><span class="sxs-lookup"><span data-stu-id="0fbd8-109">...</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="0fbd8-110">다음 코드 예제에서는 메서드를 처리 하는 단추 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="0fbd8-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event raises.</span></span> <span data-ttu-id="0fbd8-111">이 예제에서는 이러한 메서드 호출의 결과 기록 <xref:System.Windows.Controls.TextBlock> 사용 관련 요소를 get 메서드를 문자열로 새 속성 값을 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fbd8-111">The example writes the results of these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridIssharedsizescopeProp#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="0fbd8-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0fbd8-112">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>  
 [<span data-ttu-id="0fbd8-113">패널 개요</span><span class="sxs-lookup"><span data-stu-id="0fbd8-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
