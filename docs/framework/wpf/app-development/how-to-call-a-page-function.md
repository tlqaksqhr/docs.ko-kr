---
title: "방법: 페이지 함수 호출"
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
- calling page functions [WPF]
- page functions [WPF], calling
- functions [WPF], calling
ms.assetid: a4808397-c6d5-406a-83e0-0091f0c15ae4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0bc72b24b29a43e8aed073600ea863824c93ced6
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-call-a-page-function"></a><span data-ttu-id="5a5b6-102">방법: 페이지 함수 호출</span><span class="sxs-lookup"><span data-stu-id="5a5b6-102">How to: Call a Page Function</span></span>
<span data-ttu-id="5a5b6-103">페이지 함수를 호출 하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 페이지.</span><span class="sxs-lookup"><span data-stu-id="5a5b6-103">This example shows how to call a page function from a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a5b6-104">예제</span><span class="sxs-lookup"><span data-stu-id="5a5b6-104">Example</span></span>  
 <span data-ttu-id="5a5b6-105">사용 하 여 페이지 기능을 탐색할 수 있습니다는 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]것 처럼 때 페이지를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a5b6-105">You can navigate to a page function using a [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], just as you can when you navigate to a page.</span></span> <span data-ttu-id="5a5b6-106">다음 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a5b6-106">This is shown in the following example.</span></span>  
  
 [!code-csharp[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#navigatetoapagefunctionlikeapagecodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#navigatetoapagefunctionlikeapagecodebehind)]  
  
 <span data-ttu-id="5a5b6-107">데이터를 페이지 함수에 전달해야 하는 경우 인스턴스를 만든 다음 속성을 설정하여 데이터를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a5b6-107">If you need to pass data to the page function, you can create an instance of it and pass the data by setting a property.</span></span> <span data-ttu-id="5a5b6-108">또는 다음 예에 표시된 대로 기본이 아닌 생성자를 사용하여 데이터를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a5b6-108">Or, as the following example shows, you can pass the data using a non-default constructor.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#callapagefunctioncodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#callapagefunctioncodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="5a5b6-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a5b6-109">See Also</span></span>  
 <xref:System.Windows.Navigation.PageFunction%601>
