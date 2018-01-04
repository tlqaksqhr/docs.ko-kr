---
title: "방법: 계층적 XML 데이터에 마스터-세부 패턴 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0ef460664b3701f4942b8c28b8e39f891d7c871
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="9022e-102">방법: 계층적 XML 데이터에 마스터-세부 패턴 사용</span><span class="sxs-lookup"><span data-stu-id="9022e-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="9022e-103">사용 하 여 마스터-세부 정보 시나리오를 구현 하는 방법을 보여 주는이 예제 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="9022e-103">This example shows how to implement the master-detail scenario with [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9022e-104">예</span><span class="sxs-lookup"><span data-stu-id="9022e-104">Example</span></span>  
 <span data-ttu-id="9022e-105">이 예제는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터 버전의 예제에서 설명한 [마스터-세부 패턴을 사용 하 여 계층적 데이터로](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9022e-105">This example is the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="9022e-106">이 예제에서는 파일에서 데이터는 `League.xml`합니다.</span><span class="sxs-lookup"><span data-stu-id="9022e-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="9022e-107">참고 어떻게 세 번째 <xref:System.Windows.Controls.ListBox> 컨트롤의 두 번째에서 선택을 변경 내용을 추적 <xref:System.Windows.Controls.ListBox> 에 바인딩하여 해당 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9022e-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="9022e-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9022e-108">See Also</span></span>  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [<span data-ttu-id="9022e-109">방법 항목</span><span class="sxs-lookup"><span data-stu-id="9022e-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
