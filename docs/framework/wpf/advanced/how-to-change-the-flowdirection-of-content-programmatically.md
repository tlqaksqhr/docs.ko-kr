---
title: "방법: 프로그래밍 방식으로 콘텐츠의 FlowDirection 변경"
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
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ca4c94fe073fd618ca79d08812c42550594f445d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a><span data-ttu-id="ee297-102">방법: 프로그래밍 방식으로 콘텐츠의 FlowDirection 변경</span><span class="sxs-lookup"><span data-stu-id="ee297-102">How to: Change the FlowDirection of Content Programmatically</span></span>
<span data-ttu-id="ee297-103">프로그래밍 방식으로 변경 하는 방법을 보여 주는이 예제는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성은 <xref:System.Windows.Controls.FlowDocumentReader>합니다.</span><span class="sxs-lookup"><span data-stu-id="ee297-103">This example shows how to programmatically change the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property of a <xref:System.Windows.Controls.FlowDocumentReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee297-104">예제</span><span class="sxs-lookup"><span data-stu-id="ee297-104">Example</span></span>  
 <span data-ttu-id="ee297-105">두 개의 <xref:System.Windows.Controls.Button> 각각의 가능한 값 중 하나를 나타내는 요소는 만들어지지 <xref:System.Windows.FlowDirection>합니다.</span><span class="sxs-lookup"><span data-stu-id="ee297-105">Two <xref:System.Windows.Controls.Button> elements are created, each representing one of the possible values of <xref:System.Windows.FlowDirection>.</span></span> <span data-ttu-id="ee297-106">단추를 클릭 하면 연결된 된 속성 값의 내용에 적용 됩니다는 <xref:System.Windows.Controls.FlowDocumentReader> 라는 `tf1`합니다.</span><span class="sxs-lookup"><span data-stu-id="ee297-106">When a button is clicked, the associated property value is applied to the contents of a <xref:System.Windows.Controls.FlowDocumentReader> named `tf1`.</span></span>  <span data-ttu-id="ee297-107">속성 값에도 기록 됩니다는 <xref:System.Windows.Controls.TextBlock> 라는 `txt1`합니다.</span><span class="sxs-lookup"><span data-stu-id="ee297-107">The property value is also written to a <xref:System.Windows.Controls.TextBlock> named `txt1`.</span></span>  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a><span data-ttu-id="ee297-108">예제</span><span class="sxs-lookup"><span data-stu-id="ee297-108">Example</span></span>  
 <span data-ttu-id="ee297-109">위에 정의 된 단추 클릭과 연결 된 이벤트에서 처리 되는 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] 코드 숨김 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ee297-109">The events associated with the button clicks defined above are handled in a [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] code-behind file.</span></span>  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
